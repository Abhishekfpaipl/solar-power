<template>
  <div class="container mt-4">

    <CarouselBanner />
    <ImageTextSection />
    <VideoThumbnail />
    <FaqSection />
    <TestimonialSection />
    <GallerySection />
  </div>
</template>

<script>
import CarouselBanner from '@/components/CarouselBanner.vue'
import ImageTextSection from '@/components/ImageTextSection.vue'
import VideoThumbnail from '@/components/VideoThumbnail.vue'
import TestimonialSection from '@/components/TestimonialSection.vue'
import FaqSection from '@/components/FaqSection.vue'
import GallerySection from '@/components/GallerySection.vue'
export default {
  components: {
    CarouselBanner,
    ImageTextSection,
    VideoThumbnail,
    FaqSection,
    TestimonialSection,
    GallerySection,
  },
  data() {
    return {
    };
  },
};
</script>

<style scoped></style>
