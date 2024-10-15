<template>
  <div>
    <router-link to="/products" class="text-decoration-none text-dark">
      <img src="/img/banner/1.jpg" class="d-md-block d-none w-100" alt="Banner">
      <img src="/img/banner/1.jpg" class="d-md-none d-block w-100" alt="Banner">
    </router-link>
  </div>
  <!-- <div class="container my-5" v-observe>
    <div class="row g-1">
      <div class="col-4 mb-4" v-for="(card, index) in cards" :key="index">
        <div class="card rounded-0 position-relative border-0 p-2 text-white bg-dark">
          <i v-if="card.icon" :class="card.icon" class="fs-1 text-warning"></i>
          <p class="card-text smaller mb-1 text-uppercase">{{ card.description }}</p>
          <p class="card-title mb-0"><span class="fs-1 ">{{ card.title }}</span> <span class="small">%</span></p>
          <p class="text-center smaller">PLUS</p>
        </div>
      </div>
      <div class="col-12 text-muted">Compared to conventional engine oil</div>
    </div>
  </div> -->
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          title: '11',
          description: "Torque",
          icon: 'bi bi-lightning',
          backgroundImage: '/img/update.jpg',
        },
        {
          title: '22',
          description: 'Performance ',
          backgroundImage: '/img/grease.jpg',
          icon: 'bi bi-star',
        },
        {
          title: '61',
          description: "Protection",
          icon: 'bi bi-shield ',
          backgroundImage: '/img/industry.jpg',
        }
      ]
    };
  }
};
</script>

<style scoped>
.card {
  position: relative;
  overflow: hidden;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 0, 0, 0.5);
  /* opacity: 1; */
}

.card-title,
.card-text {
  position: relative;
  /* Make sure text is above the overlay */
  z-index: 1;
}

.card:hover .card-img {
  transform: scale(1.05);
}
</style>
