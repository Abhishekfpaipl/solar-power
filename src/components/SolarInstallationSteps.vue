<template>
    <div class="container">
        <h2 class="mb-5 text-start display-5" style="color: var(--bg-primary);">Steps For Successful Solar Rooftop
            Installation</h2>
        <h2 class="text-center mb-4"></h2>
        <div class="row row-cols-1 row-cols-md-2 g-2">
            <div class="col" v-for="(step, index) in steps" :key="index">
                <div class="card" style="background-color: var(--bg-primary);">
                    <div class="card-body">
                        <div class="text-start">
                            <i :class="step.icon" class="fs-1" style="color: var(--bg-secondary);"></i>
                        </div>
                        <h5 class="text-start fw-bold fs-5 text-white">{{ step.title }}</h5>
                        <ul class="row">
                            <li class="text-start text-white" v-for="(detail, detailIndex) in step.details" :key="detailIndex">
                                {{ detail }}
                            </li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SolarInstallationSteps',
    data() {
        return {
            steps: [
                {
                    title: 'Desktop simulation',
                    icon: 'bi bi-pc-display',
                    details: [
                        'We use customer inputs viz. Electricity bills, location coordinates and physical rooftop',
                        'Necessary preliminary assessment before site survey'
                    ]
                },
                {
                    title: 'Site visit',
                    icon: 'bi bi-geo-alt',
                    details: [
                        'Solar engineer visits site to validate simulation inputs and for physical assessment',
                        'Parameters viz. roof space, strength, shadow, future use etc. are assessed for discussion and finalize simulation'
                    ]
                },
                {
                    title: 'Validation and Design',
                    icon: 'bi bi-gear',
                    details: [
                        'Validation and updating of the simulation',
                        'Finalization of plant design',
                        'Plant design is prepared based on site inputs and international design principles, process and software'
                    ]
                },
                {
                    title: 'Proposal and Acceptance',
                    icon: 'bi bi-file-earmark-text',
                    details: [
                        'Preparation of optimized commercial terms and conditions',
                        'Submission of techno-commercial proposal to client',
                        'Client accepts the proposal and issues signing documents',
                        'Client gets maximum possible value',
                        'Best supplier, system, liability, and implications are offered with clear terms of business'
                    ]
                },
                {
                    title: 'Installation, Testing and Commissioning',
                    icon: 'bi bi-lightning-charge',
                    details: [
                        'Detailed design drawing prepared',
                        'Supplies, schedule and allotment',
                        'Installation of solar system',
                        'Cooperation from client is very important in this phase for swift access, availability of water, electricity etc.'
                    ]
                },
                {
                    title: 'Net Metering',
                    icon: 'bi bi-plug',
                    details: [
                        'Detailed drawings compliant with Discom rules are made and submitted to Discom',
                        'Liaison with Discom for processing',
                        'Multiple visits to engineers and staff to Discom to resolve queries and provide information',
                        'Net metering is a process between client and Discom. It is facilitated by Solar EPC companies from clients to easy completion'
                    ]
                }
            ]
        }
    }
}
</script>

<style scoped></style>