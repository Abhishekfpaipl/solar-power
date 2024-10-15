<!-- <template>
  <div class="container mt-4">
    <h2>Latest Videos</h2>
    <div class="row row-cols-2 row-cols-md-6 row-cols-8 g-3">
      <div v-for="(video, index) in videos" :key="index" class="col">
        <div class="card h-100">
          <a :href="`https://www.youtube.com/watch?v=${video.videoId}`" target="_blank">
            <img :src="video.thumbnailUrl" :alt="`Video thumbnail for ${video.title}`" class="card-img-top" />
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
      videos: [],
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
  /* width: 100%; */
  height: auto;
  border-bottom: 1px solid #ddd;
}

.card-title {
  font-size: 1rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style> -->
<template>
  <div class="container-fluid mt-4 shorts-container">
    <div class="d-flex align-items-center mb-3">
      <h2 class="mb-0 me-2">
        <i class="bi bi-lightning-charge-fill text-danger"></i> Shorts
      </h2>
      <button class="btn-close ms-auto"></button>
    </div>
    <div class="shorts-scroll">
      <div v-for="(short, index) in shorts" :key="index" class="short-card me-3">
        <div class="position-relative">
          <img :src="short.thumbnailUrl" :alt="short.title" class="short-thumbnail">
          <div class="short-overlay">
            <div class="short-title">{{ short.title }}</div>
          </div>
        </div>
        <div class="short-info mt-2">
          <div class="short-views">{{ short.views }} views</div>
          <button class="btn btn-link p-0 text-dark">
            <i class="bi bi-three-dots-vertical"></i>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      shorts: [
        {
          thumbnailUrl: 'https://picsum.photos/200/300?random=1',
          title: 'I BET U DINT KNOW 5 high paying tech skills.#coding...',
          views: '1M'
        },
        {
          thumbnailUrl: 'https://picsum.photos/200/300?random=2',
          title: 'Why Humpback Whales Attack Orcas to Protect ...',
          views: '35K'
        },
        {
          thumbnailUrl: 'https://picsum.photos/200/300?random=3',
          title: 'Reality of 80 LPA at Atlassian 🫣 ! CTC ...',
          views: '38K'
        },
        {
          thumbnailUrl: 'https://picsum.photos/200/300?random=4',
          title: 'Resume that got me interviews at Amazon, ...',
          views: '599K'
        },
        {
          thumbnailUrl: 'https://picsum.photos/200/300?random=5',
          title: 'Shantanu Sharing Secrets of Ratan TATA - These 2 ...',
          views: '2.3M'
        }
      ]
    };
  }
};
</script>

<style scoped>
.shorts-container {
  max-width: 100%;
  overflow-x: hidden;
}

.shorts-scroll {
  display: flex;
  overflow-x: auto;
  scrollbar-width: none;  /* Firefox */
  -ms-overflow-style: none;  /* Internet Explorer 10+ */
}

.shorts-scroll::-webkit-scrollbar {
  display: none;  /* WebKit */
}

.short-card {
  width: 150px;
  flex-shrink: 0;
}

.short-thumbnail {
  width: 100%;
  height: 250px;
  object-fit: cover;
  border-radius: 12px;
}

.short-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: linear-gradient(to top, rgba(0,0,0,0.7), transparent);
  padding: 10px;
  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 12px;
}

.short-title {
  color: white;
  font-size: 0.8rem;
  overflow: hidden;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

.short-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 0.8rem;
}

.short-views {
  color: #606060;
}
</style>