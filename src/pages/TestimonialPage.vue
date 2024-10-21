<template>
    <div>
        <SectionTopBanner />
        <div class="container mt-4">
            <h2>Latest Videos</h2>
            <div class="row row-cols-2 g-3">
                <div v-for="(video, index) in videos" :key="index" class="col">
                    <div class="position-relative">

                        <!-- <img :src="video.thumbnailUrl" :alt="video.title" class="rounded-4"
                                style="width: 100%; height:250px; object-fit: cover;"> -->
                        <div class="" style="height:250px;">
                            <iframe style="width: 100%;height: 100%;"
                                :src="`https://www.youtube.com/embed/${video.videoId}`" frameborder="0"
                                allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                                allowfullscreen>
                            </iframe>

                        </div>

                        <!-- <img :src="video.thumbnailUrl" :alt="video.title" class="rounded-4"
                            style="width: 100%; height:250px; object-fit: cover;"> -->
                        <div class="short-overlay">
                            <div class="short-title">{{ video.title }}</div>
                        </div>
                    </div>
                    <div class="short-info mt-2">
                        <div class="short-views">{{ video.viewCount }} views</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
import axios from "axios";
import SectionTopBanner from '@/components/SectionTopBanner.vue'

export default {
    components: {
        SectionTopBanner
    },
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
            // const apiKey = "AIzaSyB78gC2yfrEe7GzdQXJVG-ZmQESLWAwRnM";
            const apiKey = "AIzaSyDIJw8aJPUCKW4q2Kqq-mlYnFZ8Eq4Anis";
            // const channelId = "UCIgE6BvgzK3nSnesZPJy2wQ";
            const channelId = "UC9Z3-5kyCd5ng_ghfuare4w";
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
<style>
.short-thumbnail {
    width: 100%;
    height: 250px;
    object-fit: cover;
    border-radius: 12px;
}
</style>