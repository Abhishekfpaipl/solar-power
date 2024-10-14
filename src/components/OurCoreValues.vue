<template>
    <div>
        <div class="container pt-4">
            <div class="text-start mb-5">
                <p class="text-muted mb-1 text-uppercase">Check</p>
                <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);">Our Core Values</h2>
            </div>
            <p class="text-start container">
                One thing that we've tried to keep consistent through all these years is our core set of values and
                beliefs.
                They have helped us get to where we are today, and they guide us as we grow. We inculcate these
                values
                in
                everything we do - from the littlest of things to the biggest of decisions.
            </p>
            <div class="p-2 row">
                <div v-for="(data, index) in datas" :key="index" class="col-12 col-md-6 g-3">
                    <div class="d-md-flex align-items-center p-2"
                        style=" min-height: 120px; border: 1px solid var(--bg-primary);">
                        <i :class="data.icon" class="fs-2 mx-3" style="color: var(--bg-primary)"></i>
                        <div class=" ms-2 text-md-start">
                            <span class="fw-bold">{{ data.heading }}</span>
                            <p class="mb-0">{{ data.text }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            datas: [
                {
                    icon: 'bi bi-lightbulb',
                    heading: 'High Performance',
                    text: 'Our products are engineered for superior performance, delivering exceptional results in diverse applications.'
                },
                {
                    icon: 'bi bi-person',
                    heading: 'Temperature Control',
                    text: 'We develop solutions that maintain optimal performance across a wide range of temperatures.'
                },
                {
                    icon: 'bi bi-people',
                    heading: 'Eco-Friendly',
                    text: 'We are committed to environmentally sustainable practices, ensuring our products and processes minimize environmental impact.'
                },
                {
                    icon: 'bi bi-check2-all',
                    heading: 'Advanced Infrastructure',
                    text: 'We use cutting-edge technology and labs to deliver products that meet API and NLGI standards.'
                },
                {
                    icon: 'bi bi-gear',
                    heading: 'Integrity',
                    text: 'We uphold the highest standards of integrity in all aspects of our business.'
                },
                {
                    icon: 'bi bi-graph-up',
                    heading: 'Diligence',
                    text: 'Our leadership fosters strong work ethics and promotes transparency throughout the organization.'
                },
                {
                    icon: 'bi bi-graph-up',
                    heading: 'Respect',
                    text: 'We build strong relationships by treating all individuals and partners with respect and consideration'
                },
                {
                    icon: 'bi bi-graph-up',
                    heading: 'Flexibility',
                    text: 'We offer custom formulations and tailored packaging to meet unique customer needs.'
                },
                {
                    icon: 'bi bi-graph-up',
                    heading: 'Quality Control',
                    text: 'We ensure top quality and adhere to global standards, with certifications like ISO 9001:2015 and TS 16949:2009.'
                },
            ],
        }
    },
}
</script>
<style lang="">

</style>