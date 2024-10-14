<template>
    <div class="position-fixed w-100 d-flex justify-content-between  align-items-center p-4 top-0 bg-dark"
        style="z-index: 10;">
        <router-link to="/">
            <img src="img/logo.png" alt="" style="height: 50px;">
        </router-link>
        <div class="d-none d-md-flex align-items-center gap-3">
            <router-link :to="link.route" class="text-decoration-none text-white" v-for="(link, index) in links"
                :key="index">{{ link.name }}</router-link>
        </div>
        <i class="bi bi-list fs-1 d-md-none d-block text-white" data-bs-toggle="offcanvas" data-bs-target="#MobileMenu"
            aria-controls="MobileMenu"></i>
    </div>
    <div class="offcanvas offcanvas-end" style="background-color: var(--bg-primary)" tabindex="-1" id="MobileMenu"
        aria-labelledby="MobileMenuLabel">
        <div class="offcanvas-header border-bottom d-flex justify-content-between align-items-center">
            <img src="img/logo.png" alt="" style="height: 40px;">
            <i class="bi bi-x fs-1 text-white" data-bs-dismiss="offcanvas" aria-label="Close"></i>
        </div>
        <div class="offcanvas-body px-0">
            <div class="d-flex flex-column align-items-start gap-3">
                <router-link :to="link.route" class="text-decoration-none text-dark w-100 border-bottom px-3"
                    v-for="(link, index) in links" :key="index">
                    <p data-bs-dismiss="offcanvas" class="text-start mb-0">{{ link.name }}</p>
                </router-link>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "TopNav",
    data() {
        return {
            links: [
                { name: 'Home', route: '/' },
                { name: 'About Us', route: '/about-us' },
                { name: 'Contact Us', route: '/contact-us' },
                { name: 'Career', route: '/career' },
                { name: 'Benefit', route: '/benefit' },
                { name: 'Dealership', route: '/dealership' },
            ]
        }
    }
}
</script>
<style lang="">

</style>