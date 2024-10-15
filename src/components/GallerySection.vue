<template>
  <div class="container" v-observe>
    <div class="text-start mb-5">
      <p class="text-muted mb-1 text-uppercase">Ariseol</p>
      <h2 class="display-5  text-uppercase" style="color: var(--bg-primary);">Check Our Gallery</h2>
    </div>
    <div class="row row-cols-2 row-cols-md-2 row-cols-lg-3 row-cols-xl-4 g-2">
      <div class="col" v-for="(image, index) in images " :key="index" data-bs-toggle="modal"
        data-bs-target="#exampleModal">
        <div class="card rounded-0 border-0 overflow-hidden">
          <img :src="image" alt="Gallery" class="w-100" style="height: 300px;object-fit: cover;">
        </div>
      </div>
    </div>
    <!-- <div class="mt-3 text-end">
      <router-link to="/gallery" class="text-decoration-none text-danger">More <i
          class="bi bi-arrow-right"></i></router-link>
    </div> -->
  </div>

  <!-- Modal -->
  <div class="modal fade p-0" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
    <div class="modal-dialog modal-fullscreen">
      <div class="modal-content bg-transparent">
        <div class="modal-body p-0">
          <div id="carouselExampleIndicators" class="carousel slide d-flex justify-content-center align-items-center">
            <div class="carousel-indicators">
              <button v-for="(image, index) in images" :key="'indicator-' + index" type="button"
                :data-bs-target="'#carouselExampleIndicators'" :data-bs-slide-to="index"
                :class="{ 'active': index === activeIndex }" :aria-current="index === activeIndex ? 'true' : undefined"
                :aria-label="'Slide ' + (index + 1)"></button>
            </div>
            <div class="carousel-inner">
              <div v-for="(image, index) in images" :key="'carousel-item-' + index" class="carousel-item"
                :class="{ 'active': index === activeIndex }">
                <img :src="image" class="vh-100 vw-100" alt="..." style="object-fit: contain;" data-bs-dismiss="modal">
              </div>
            </div>
            <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators"
              data-bs-slide="prev">
              <span class="carousel-control-prev-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Previous</span>
            </button>
            <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators"
              data-bs-slide="next">
              <span class="carousel-control-next-icon" aria-hidden="true"></span>
              <span class="visually-hidden">Next</span>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GallerySection",
  data() {
    return {
      images: [
        "/img/gallery/1.jpg",
        "/img/gallery/2.jpg",
        "/img/gallery/3.jpg",
        "/img/gallery/4.jpg",
        // "/img/gallery/5.jpg",
        // "/img/gallery/6.jpg",
        // "/img/gallery/7.jpg",
        // "/img/gallery/8.jpg",
        // "/img/gallery/9.jpg",
      ],
      activeIndex: 0
    }
  },
};
</script>

<style scoped>
.card:hover img {
  transform: scale(1.1);
  transition: transform 0.5s ease;
}

.before-enter {
  opacity: 0;
  transform: translateY(80px);
  transition: opacity 1.5s ease-out, transform 1.5s ease-out;
}

.enter {
  opacity: 1;
  transform: translateY(0);
}
</style>
