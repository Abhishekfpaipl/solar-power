<template>
  <CarouselBanner />
  <div class="container">
    <div class="my-5">
      <WhyGoSolar />
    </div>
    <div class="my-5">
      <ImageTextSection />
    </div>
    <div class="my-5">
      <SolarAdvantages />
    </div>
    <div class="my-5">
      <SolarInstallationSteps />
    </div>
    <div class="my-5">
      <VideoThumbnail />
    </div>
    <div class="my-5">
      <FaqSection />
    </div>
    <div class="my-5">
      <TestimonialSection />
    </div>
    <div class="my-5">
      <GallerySection />
    </div>
  </div>
</template>

<script>
import CarouselBanner from '@/components/CarouselBanner.vue'
import WhyGoSolar from '@/components/WhyGoSolar.vue'
import ImageTextSection from '@/components/ImageTextSection.vue'
import SolarAdvantages from '@/components/SolarAdvantages.vue'
import SolarInstallationSteps from '@/components/SolarInstallationSteps.vue'
import VideoThumbnail from '@/components/VideoThumbnail.vue'
import TestimonialSection from '@/components/TestimonialSection.vue'
// import FaqSection from '@/components/FaqSection.vue'
import GallerySection from '@/components/GallerySection.vue'
export default {
  components: {
    CarouselBanner,
    WhyGoSolar,
    ImageTextSection,
    SolarAdvantages,
    SolarInstallationSteps,
    VideoThumbnail,
    // FaqSection,
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
