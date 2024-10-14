<template>
  <div>
    <div class="container py-3">
      <div class="text-start mb-5">
        <p class="text-muted mb-1 text-uppercase">Our</p>
        <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);"> Production Team</h2>
      </div>
      <div class="position-relative">
        <div class="d-flex gap-3 overflow-x-scroll" ref="techScrollContainer" id="scroll">
          <div class="" v-for="(team, index) in techTeam" :key="index">
            <div class="card rounded-0" style="min-width: 18rem; border:1px solid var(--bg-primary)">
              <div class="card-body p-0">
                <div class="text-center card-title py-2 bg-light" style="border-bottom:1px solid var(--bg-primary)">
                  <h5 class="lh-1 mb-0">{{ team.name }}</h5>
                  <small>{{ team.post }}</small>
                </div>
                <p class="px-2 text-ellipsis4">{{ team.value }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="rounded-circle border d-flex justify-content-center align-items-center position-absolute bg-light"
          @click="scrollLeft($refs.techScrollContainer)" style="width: 40px; height:40px ;top: 40%; left: -2%">
          <i class="bi bi-chevron-left"></i>
        </div>
        <div class="rounded-circle border d-flex justify-content-center align-items-center position-absolute bg-light"
          @click="scrollRight($refs.techScrollContainer)" style="width: 40px; height:40px ;top: 40%; right: -2%">
          <i class="bi bi-chevron-right"></i>
        </div>
      </div>
    </div>

    <div class="container py-3 my-5">
      <div class="text-start mb-5">
        <p class="text-muted mb-1 text-uppercase">Our</p>
        <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);"> Marketing Team</h2>
      </div>
      <div class="position-relative">
        <div class="d-flex gap-3 overflow-x-scroll" ref="marketingScrollContainer" id="scroll">
          <div class="" v-for="(team, index) in marketingTeam" :key="index">
            <div class="card rounded-0" style="min-width: 18rem; border:1px solid var(--bg-primary)">
              <div class="card-body p-0">
                <div class="text-center card-title py-2 bg-light" style="border-bottom:1px solid var(--bg-primary)">
                  <h5 class="lh-1 mb-0">{{ team.name }}</h5>
                  <small>{{ team.post }}</small>
                </div>
                <p class="px-2 text-ellipsis4">{{ team.value }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="rounded-circle border d-flex justify-content-center align-items-center position-absolute bg-light"
          @click="scrollLeft($refs.marketingScrollContainer)" style="width: 40px; height:40px ;top: 40%; left: -2%">
          <i class="bi bi-chevron-left"></i>
        </div>
        <div class="rounded-circle border d-flex justify-content-center align-items-center position-absolute bg-light"
          @click="scrollRight($refs.marketingScrollContainer)" style="width: 40px; height:40px ;top: 40%; right: -2%">
          <i class="bi bi-chevron-right"></i>
        </div>
      </div>
    </div>

    <div class="container py-3 my-5">
      <div class="text-start mb-5">
        <p class="text-muted mb-1 text-uppercase">Our</p>
        <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);"> Management Team</h2>
      </div>
      <div class="position-relative">
        <div class="d-flex gap-3 overflow-x-scroll" ref="managementScrollContainer" id="scroll">
          <div class="" v-for="(team, index) in managementTeam" :key="index">
            <div class="card rounded-0" style="min-width: 18rem; min-height: 12rem; border:1px solid var(--bg-primary)">
              <div class="card-body p-0">
                <div class="text-center card-title py-2 bg-light" style="border-bottom:1px solid var(--bg-primary)">
                  <h5 class="lh-1 mb-0">{{ team.name }}</h5>
                  <small>{{ team.post }}</small>
                </div>
                <p class="card-text px-2 text-ellipsis4">{{ team.value }}</p>
              </div>
            </div>
          </div>
        </div>
        <div class="rounded-circle border d-flex justify-content-center align-items-center position-absolute bg-light"
          @click="scrollLeft($refs.managementScrollContainer)" style="width: 40px; height:40px ;top: 40%; left: -2%">
          <i class="bi bi-chevron-left"></i>
        </div>
        <div class="rounded-circle border d-flex justify-content-center align-items-center position-absolute bg-light"
          @click="scrollRight($refs.managementScrollContainer)" style="width: 40px; height:40px ;top: 40%; right: -2%">
          <i class="bi bi-chevron-right"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'InfoSection',
  props: {
    techTeam: {
      type: Array,
      required: true
    },
    managementTeam: {
      type: Array,
      required: true
    },
    marketingTeam: {
      type: Array,
      required: true
    },
  },
  methods: {
    scrollLeft(container) {
      const scrollWidth = container.clientWidth;
      const newScrollLeft = Math.max(container.scrollLeft - scrollWidth, 0);

      container.scrollTo({
        left: newScrollLeft,
        behavior: 'smooth'
      });
    },
    scrollRight(container) {
      const scrollWidth = container.clientWidth;
      const maxScrollLeft = container.scrollWidth - scrollWidth;
      const newScrollLeft = Math.min(container.scrollLeft + scrollWidth, maxScrollLeft);

      container.scrollTo({
        left: newScrollLeft,
        behavior: 'smooth'
      });
    }
  }
}
</script>

<style scoped>
/* .card-text {
  max-height: 12rem;
  overflow-y: auto;
} */

#scroll::-webkit-scrollbar {
  display: none;
}
</style>
