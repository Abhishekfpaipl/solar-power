<template>
    <div style="padding-top: 66px;">

        <SectionTopBanner />
        <div class="container " v-observe>
            <div class="row p-3">
                <div class="col-12 pt-4 text-center">
                    <form @submit.prevent="submitQuery()" class="mt-4 row g-3 needs-validation" novalidate>
                        <div class="w-100 form-floating mt-0">
                            <input type="text" class="form-control" placeholder="" v-model="name" required>
                            <label for="floatingInput" class="text-muted ms-2">Name</label>
                        </div>
                        <div class="w-100 form-floating mt-2">
                            <input type="number" class="form-control" placeholder="Mobile" v-model="number" required>
                            <label class="ms-2 text-muted">Mobile No</label>
                        </div>
                        <div class="w-100 form-floating mt-2">
                            <input type="email" class="form-control" placeholder="Email" v-model="email" required>
                            <label class="ms-2 text-muted">Email Id</label>
                        </div>
                        <div class="w-100 form-floating mt-2">
                            <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextarea"
                                v-model="note"></textarea>
                            <label for="floatingTextarea" class="ms-2 text-muted">Describe your requirements</label>
                        </div>
                        <div class="col-12">
                            <button class="btn btn-danger py-2 fs-5 w-100 rounded-0 text-white"
                                type="submit">Submit</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
        <div class="container-fluid mt-5 py-5 bg-dark text-white" v-observe>
            <div class="row justify-content-center align-items-center">
                <h1 class="text-uppercase mb-4 text-center">Need to get in touch with us?</h1>
                <div class="col-12 col-md-6 mt-5 mt-md-0 ">
                    <div class="row row-cols-1">
                        <div v-for="(icon, index) in contact" :key="index" class="col py-2"
                            @click="handleIconClick(icon.action)">
                            <div class="d-flex justify-content-start align-items-center border p-2 ps-3">
                                <a class="text-white" :href="icon.url" target="_blank">
                                    <i :class="icon.icon" class="primary-text fs-1"></i>
                                </a>
                                <p class="text-start ms-2 fw-bold mb-0">{{ icon.name }}</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="col-12 col-md-6 d-flex align-items-center justify-content-center">
                    <img src="/img/contactus.png" style="width: 100%;" alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import SectionTopBanner from "@/components/SectionTopBanner.vue";
export default {
    name: "ContactPage",
    components: {
        SectionTopBanner,
    },
    data() {
        return {
            contact: [
                { name: ' info@clgoilindia.com', icon: 'bi-envelope', color: 'red', action: 'openEmail' },
                { name: ' HD-723, WeWork Enam Sambhav, C - 20, G Block Rd, G-Block BKC, Bandra Kurla Complex, Bandra East, Mumbai, Maharashtra - 400051', icon: 'bi-geo-fill', color: 'black', action: 'openMaps' },
            ],
            name: '',
            number: '',
            email: '',
            note: '',
        }
    },
    methods: {
        handleIconClick(action) {
            const phoneNumber = '+919711256073';
            const emailAddress = 'info@clgoilindia.com';
            const location = 'HD-723, WeWork Enam Sambhav, C - 20, G Block Rd, G-Block BKC, Bandra Kurla Complex, Bandra East, Mumbai, Maharashtra - 400051';

            switch (action) {
                case 'openEmail':
                    window.location.href = `mailto:${emailAddress}`;
                    break;
                case 'openDialer':
                    window.location.href = `tel:${phoneNumber}`;
                    break;
                case 'openWhatsapp':
                    window.open(`https://wa.me/${phoneNumber}?text=Hello...`, '_blank');
                    break;
                case 'openMaps':
                    window.open(`https://www.google.com/maps/search/?api=1&query=${encodeURIComponent(location)}`, '_blank');
                    break;
                default:
                    break;
            }
        },
        submitQuery() { 
            console.log('send');
            this.name = "",
            this.number = "",
            this.email = "",
            this.note = "";
        }
    },
}
</script>

<style scoped>
.cutout {
    overflow: hidden;
    text-align: center;
}

.cutout>span {
    position: relative;
    display: inline-block;
}

.cutout>span:before,
.cutout>span:after {
    content: "";
    position: absolute;
    top: 50%;
    width: 900px;
    /* Adjust width as needed */
    margin: 0 20px;
}

.cutout>span:before {
    right: 100%;
    border-bottom: 2px solid;
    border-color: red;
    border-image-slice: 1;
}

.cutout>span:after {
    left: 100%;
    border-bottom: 2px solid;
    border-color: red;
    border-image-slice: 1;
}
</style>
