<template>
    <div class="container-fluid bg-dark text-white py-5 why-go-solar"
        style="background-image: url('/img/banner/1.jpg')">
        <div class="overlay"></div> <!-- Overlay div -->
        <div class="container position-relative">
            <h2 class="mb-5 text-start display-5">Why Go Solar?</h2>
            <!-- <h2 class="text-center mb-5">Why Go Solar?</h2> -->
            <div class="row justify-content-center">
                <div v-for="(reason, index) in reasons" :key="index" class="col-md-4 mb-4">
                    <div class="card bg-transparent text-white h-100 border-light">
                        <div class="card-body text-center">
                            <div class="display-4 mb-3 text-start">
                                <i :class="reason.icon" class="bi"></i>
                            </div>
                            <ul class="list-unstyled">
                                <li v-for="(point, pointIndex) in reason.points" :key="pointIndex"
                                    class="text-start mb-2">
                                    <i class="bi bi-check-circle-fill text-success me-2"></i>
                                    {{ point }}
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'WhyGoSolar',
    data() {
        return {
            reasons: [
                {
                    icon: 'bi-globe',
                    points: [
                        'Solar is the fastest growing sector in India and world.',
                        'Clean, green and cheaper electricity.'
                    ]
                },
                {
                    icon: 'bi-lightbulb',
                    points: [
                        'Use your vacant roof space to reduce electricity bills substantially.',
                        'Roof can still be used, if wanted.'
                    ]
                },
                {
                    icon: 'bi-coin',
                    points: [
                        'One time investment.',
                        'Electricity for 25 years or more.',
                        'Payback in 3-5 years.',
                        'No more continuously increasing grid tariff.'
                    ]
                }
            ]
        }
    }
}
</script>

<style scoped>
.why-go-solar {
    position: relative;
    /* background-image: url('/img/banner/1.jpg'); */
    background-size: cover;
    background-position: center;
    color: white;
}

.overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    /* Adjust the opacity as needed */
    z-index: 1;
}

.container {
    position: relative;
    z-index: 2;
    /* Make sure content is above the overlay */
}
</style>
