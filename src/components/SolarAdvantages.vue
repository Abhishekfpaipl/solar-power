<template>
    <div class="container">
        <h2 class="mb-5 text-start display-5" style="color: var(--bg-primary);">Get The Exolar Advantage, We Understand
            Better</h2>

        <div class="row row-cols-1 row-cols-md-2 g-4">
            <div class="col" v-for="(advantage, index) in advantages" :key="index">
                <div class="card h-100" style="background-color: var(--bg-primary);">
                    <div class="card-body">
                        <div class="d-flex align-items-center mb-3">
                            <i :class="advantage.icon" class="fs-1 me-3"
                                style="color: var(--bg-secondary);"></i>
                            <h5 class="text-white  mb-0">{{ advantage.title }}</h5>
                        </div>
                        <p class="text-start text-white">{{ advantage.description }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SolarAdvantages',
    data() {
        return {
            advantages: [
                {
                    title: 'Strong top Management',
                    description: 'Exolar is founded by solar sector professionals with qualification from IIT and deep experience across the value chain viz. design.',
                    icon: 'bi bi-gear-fill'
                },
                {
                    title: 'Engineering excellence',
                    description: 'Expertise along the value chain. Our strong engineering team helps get the maximum value.',
                    icon: 'bi bi-stars'
                },
                {
                    title: 'Transparency',
                    description: 'We are transparent. We value our partnership. We offer multiple combinations for you to choose from. We are available for discussions, always.',
                    icon: 'bi bi-search'
                },
                {
                    title: 'Deep Knowledge of Equipment',
                    description: 'Through experience and knowledge of and relationship with leading equipment manufacturers.',
                    icon: 'bi bi-lightbulb-fill'
                },
                {
                    title: 'Best Techno-Commercial Offer',
                    description: 'We offer the best solution that focuses on both technology and commercial aspects without compromise any one of them.',
                    icon: 'bi bi-file-earmark-text-fill'
                },
                {
                    title: 'Execution Excellence',
                    description: 'Execution team combines knowledge of equipment, engineering and project management practices for effective and efficient execution.',
                    icon: 'bi bi-graph-up-arrow'
                },
                {
                    title: 'Top of the class O&M Practices',
                    description: 'We follow best proactive and preventive maintenance practices to give your plant smooth operation and maximum possible generation',
                    icon: 'bi bi-clipboard-check-fill'
                },
                {
                    title: 'Remote Monitoring and Data Analytics',
                    description: 'We put the control of the plant in your hands through data collection and periodic analysis so that you understand the parameters easily.',
                    icon: 'bi bi-pc-display-horizontal'
                }
            ]
        }
    }
}
</script>

<style scoped></style>