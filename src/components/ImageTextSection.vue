<template>
    <div class="container my-5">
        <h2 class="mb-5 text-start display-5" style="color: var(--bg-primary);">CHECK OUR DETAILS</h2>
        <div class="row mb-5">
            <div class="col-md-6" v-observe>
                <img src="/img/1.jpg" alt="Illustration" class="img-fluid">

            </div>
            <div class="col-md-6 d-flex flex-column justify-content-center mt-4 mt-md-0 text-start" v-observe>
                <h3 class=" mb-3" style="color: var(--bg-primary);">DRIVING THE CHANGE
                </h3>
                <p class="mb-4">We at Vikram Solar are focused towards contributing to national and global solar
                    transition targets. With extensive experience is commissioning ground mounted and rooftop projects
                    for Government and private entities, in utility, health, education, industry and consumer sectors,
                    and impressive portfolio of advanced technology modules we are advancing in creating climate for
                    change.</p>
                <!-- <ul class="list-unstyled">
                    <li class="mb-2">
                        <i class="bi bi-check2  me-2" style="color: var(--bg-primary);"></i>
                        Optimized for heavy-duty machinery, ensuring smooth operation under extreme conditions.
                    </li>
                    <li class="mb-2">
                        <i class="bi bi-check2   me-2" style="color: var(--bg-primary);"></i>
                        Formulated to reduce energy consumption and minimize equipment wear.
                    </li>
                    <li class="mb-2">
                        <i class="bi bi-check2   me-2" style="color: var(--bg-primary);"></i>
                        Provides superior protection against rust, corrosion, and oxidation.
                    </li>
                </ul> -->
            </div>

        </div>

        <div class="row mb-5">
            <div class="col-md-6 order-md-2" v-observe>
                <img src="/img/2.jpg" alt="Illustration" class="img-fluid">
            </div>
            <div class="col-md-6 order-md-1 d-flex flex-column justify-content-center text-start" v-observe>
                <h3 class=" mb-3" style="color: var(--bg-primary);">ENABLING
                    A GREEN FUTURE</h3>
                <p class="mb-4">Creating climate for change through thought leadership and raising awareness towards
                    solar industry, aiding in realisation of Aatmanirbhar and energy-rich India.</p>

            </div>

        </div>

        <div class="row mb-5">
            <div class="col-md-6" v-observe :class="imageClass('left')">
                <img src="/img/3.jpg" alt="Illustration" class="img-fluid">
            </div>
            <div class="col-md-6 d-flex flex-column justify-content-center text-start" v-observe>
                <h3 class=" mb-3" style="color: var(--bg-primary);">Leaders in Oil and Grease Manufacturing</h3>
                <p class="mb-4">Our industry is at the forefront of producing high-performance oils and greases that
                    meet the demands of various sectors, from automotive to heavy machinery and industrial equipment.
                </p>
                <p>We specialize in advanced formulations that enhance machinery efficiency, reduce wear, and extend the
                    lifespan of equipment. Our products are designed to operate under extreme conditions, providing
                    reliable lubrication, protection against corrosion, and optimal performance for a wide range of
                    applications. With a focus on sustainability, we continuously innovate to deliver solutions that
                    help reduce energy consumption and environmental impact.</p>
            </div>

        </div>
    </div>
</template>

<script>
export default {
    name: 'ImageTextSection',
    props: {
        mobile: {
            type: Number,
        },
        imageSrc: {
            type: String,
            required: true
        },
        imageAlt: {
            type: String,
            default: ''
        },
        title: {
            type: String,
        },
        heading: {
            type: String,
        },
        subHeading: {
            type: String,
        },
        text: {
            type: String,
        },
        imageFirst: {
            type: Boolean,
            default: true
        },
        points: {
            type: Array,
        },
        button: {
            type: Boolean,
        }
    },
    methods: {
        imageClass(position) {
            return {
                'before-enter-right': position === 'right',
                'before-enter-left': position === 'left'
            };
        },
        textClass(position) {
            return {
                'before-enter-left': position === 'right',
                'before-enter-right': position === 'left'
            };
        }
    }
}
</script>

<style scoped>
.img-fluid {
    max-width: 100%;
    height: auto;
}
</style>
