<template>
  <div class="container mt-4">
    <h2>Latest Videos</h2>
    <div class="row">
      <div
        v-for="(video, index) in videos"
        :key="index"
        class="col-md-4 col-sm-6 col-lg-3 mb-4"
      >
        <div class="card">
          <a :href="`https://www.youtube.com/watch?v=${video.videoId}`" target="_blank">
            <img
              :src="video.thumbnailUrl"
              :alt="`Video thumbnail for ${video.title}`"
              class="card-img-top"
            />
          </a>
          <div class="card-body">
            <h5 class="card-title">{{ video.title }}</h5>
            <p class="card-text">{{ video.viewCount }} views</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      videos: [], // Array to hold multiple videos
    };
  },
  created() {
    this.fetchAllVideos();
  },
  methods: {
    async fetchAllVideos() {
      const apiKey = "AIzaSyB78gC2yfrEe7GzdQXJVG-ZmQESLWAwRnM";
      const channelId = "UCIgE6BvgzK3nSnesZPJy2wQ";
      const url = `https://www.googleapis.com/youtube/v3/search?part=snippet&channelId=${channelId}&maxResults=10&order=date&type=video&key=${apiKey}`;

      try {
        const response = await axios.get(url);
        const data = response.data;

        // Check if videos are returned
        if (data.items && data.items.length > 0) {
          this.videos = data.items.map(async (item) => {
            // Fetch video details for view count
            const videoDetailsUrl = `https://www.googleapis.com/youtube/v3/videos?part=statistics&id=${item.id.videoId}&key=${apiKey}`;
            const videoDetailsResponse = await axios.get(videoDetailsUrl);
            const viewCount = videoDetailsResponse.data.items[0].statistics.viewCount;

            return {
              videoId: item.id.videoId,
              thumbnailUrl: item.snippet.thumbnails.high.url,
              title: item.snippet.title,
              viewCount: this.formatViewCount(viewCount),
            };
          });
          this.videos = await Promise.all(this.videos);
        }
      } catch (error) {
        console.error("Error fetching YouTube data:", error);
      }
    },
    formatViewCount(count) {
      if (count >= 1000000) {
        return (count / 1000000).toFixed(1) + 'M';
      }
      if (count >= 1000) {
        return (count / 1000).toFixed(1) + 'K';
      }
      return count;
    },
  },
};
</script>

<style scoped>
.card {
  border-radius: 12px;
  overflow: hidden;
}

.card-img-top {
  width: 100%;
  height: auto;
  border-bottom: 1px solid #ddd;
}

.card-title {
  font-size: 1rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.card-text {
  font-size: 0.9rem;
  color: #666;
}

.container {
  max-width: 1200px;
}
</style>
