<template>
    <div class="container">
        <div class="text-start mb-5">
            <p class="text-muted mb-1 text-uppercase">Ariseol</p>
            <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);">Our Motor Oil</h2>
        </div>
        <div class="row">
            <div class="col-md-6 position-relative">
                <img src="/img/ourBenefit.jpg" alt="Why choose us" class="img-fluid w-100">
            </div>
            <div class="col-md-6 text-start">
                <div class="accordion" id="accordionExample">
                    <div class="accordion-item rounded-0" v-for="(item, index) in benefits.slice(0, 4)" :key="index">
                        <h2 class="accordion-header">
                            <button class="accordion-button fw-bold text-dark" type="button" data-bs-toggle="collapse"
                                :data-bs-target="'#collapseOne' + index" aria-expanded="true"
                                :aria-controls="'collapseOne' + index">
                                {{ item.title }}
                            </button>
                        </h2>
                        <div :id="'collapseOne' + index" class="accordion-collapse collapse"
                            :class="{ show: index === 0 }" data-bs-parent="#accordionExample">
                            <div class="accordion-body text-start">
                                {{ item.content }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <router-link to="/benefit" class="text-end text-decoration-none text-danger mb-5 mt-3">More <i
                    class="bi bi-arrow-right"></i></router-link>
        </div>
    </div>

</template>

<script>
export default {
    name: 'WhyUsComponent',
    data() {
        return {
            accordionData: [
                {
                    title: "Atmospheric Style Soap Manufacturing Vessels (Kettles)",
                    content: "These vessels are designed for the efficient production of soap-based greases. They operate under atmospheric pressure, ensuring controlled reactions and consistent product quality.",
                },
                {
                    title: "20 MT/day Grease Production Facilities",
                    content: "Our facilities are equipped to produce up to 20 metric tons of grease per day. This ensures high capacity and meeting large-scale production demands.",
                },
                {
                    title: "25 KL/day Lube Blending Facilities",
                    content: "We offer lube blending capabilities of 25 kiloliters per day. This facilitates the precise mixing of lubricants to achieve the desired formulations and quality.",
                },
                {
                    title: "High-Speed Shear for Non-Soap Thickened Greases",
                    content: "Our high-speed shear facilities are particularly effective for processing non-soap thickened greases. This enhances the consistency and performance of these specialized products.",
                },
                {
                    title: "High-Pressure Milling",
                    content: "This process ensures the fine grinding and uniform dispersion of grease components. This results in improved texture and performance.",
                },
                {
                    title: "Grease De-Aeration",
                    content: "Our de-aeration systems remove trapped air from greases. This helps in achieving a smooth, bubble-free product and enhances its stability and performance.",
                },
                {
                    title: "Oil Blending Facilities",
                    content: "We provide advanced oil blending capabilities to ensure the precise formulation of lubricants and greases. This optimizes their effectiveness and compatibility.",
                },
                {
                    title: "Steam and Thermal Oil Heating",
                    content: "Our heating systems utilize steam and thermal oil to maintain optimal temperatures during production. This ensures consistent quality and efficiency.",
                },
                {
                    title: "Bulk Storage Facilities",
                    content: "Our bulk storage solutions are designed to safely and efficiently handle large quantities of raw materials and finished products. This ensures easy access and inventory management.",
                },
                {
                    title: "Advanced Filling and Packing Machines",
                    content: "State-of-the-art filling and packing equipment ensure accurate, efficient, and hygienic packaging of greases and lubricants. This meets industry standards and customer requirements.",
                },
            ],
            benefits: [
                {
                    "title": "Excellent Engine Sludge & Varnish Control",
                    "content": "Provides superior control over sludge and varnish deposits, keeping the engine cleaner for better performance and longer life."
                },
                {
                    "title": "Cold Start Optimization",
                    "content": "Ensures better cold start properties, improving engine startup in low-temperature conditions and reducing wear."
                },
                {
                    "title": "Superior Wear Protection",
                    "content": "Offers excellent protection against engine wear, ensuring longevity and reducing maintenance needs."
                },
                {
                    "title": "Thermal and Oxidation Stability",
                    "content": "Provides excellent thermal and oxidation stability, ideal for heavy-duty applications where extreme heat is a concern."
                },
                {
                    "title": "Enhanced Oil and Engine Life",
                    "content": "Enhances both oil and engine life through superior oxidation and wear protection, ensuring smoother performance."
                },
                {
                    "title": "Friction Optimization for Wet Clutches",
                    "content": "Possesses special frictional properties required for smooth operation of wet clutches in 4-stroke 2-wheelers."
                },
                {
                    "title": "Outstanding Oxidation Stability",
                    "content": "Offers exceptional oxidation stability, ensuring a cleaner engine and extending the oil's life."
                },
                {
                    "title": "Minimized Engine Deposits",
                    "content": "Minimizes engine deposits due to excellent sludge and varnish control, keeping the engine components cleaner."
                },
                {
                    "title": "Oil Film Strength",
                    "content": "Provides adequate oil film strength to protect the engine under all operating temperatures, ensuring reliable performance."
                },
                {
                    "title": "High Detergency for Cleaner Engine",
                    "content": "Ensures a high level of detergency, keeping the engine clean from harmful deposits and debris."
                },
                {
                    "title": "High Thermal Stability",
                    "content": "Minimizes oil degradation with high thermal stability, especially in extreme operating conditions."
                },
                {
                    "title": "Shear Stability for Viscosity Retention",
                    "content": "Provides high shear stability to retain oil viscosity, ensuring consistent protection over time."
                },
                {
                    "title": "Longer Drain Interval",
                    "content": "Allows for extended drain intervals, reducing the need for frequent oil changes and lowering maintenance costs."
                },
                {
                    "title": "Fuel Efficiency Enhancement",
                    "content": "Improves fuel efficiency by reducing petrol consumption, benefiting both performance and cost-effectiveness."
                },
                {
                    "title": "All-Season Compatibility",
                    "content": "Suitable for use in all seasons, helping to reduce oil consumption and providing consistent protection."
                },
                {
                    "title": "Extended Oil Life",
                    "content": "Extends oil life through excellent oxidation and nitration resistance, reducing the frequency of oil changes."
                },
                {
                    "title": "Optimized Ash Content",
                    "content": "Prolongs the life of valves and spark plugs by optimizing ash content, ensuring smooth engine operation."
                },
                {
                    "title": "Piston and Engine Cleanliness",
                    "content": "Keeps pistons and engines clean, ensuring smoother engine operation and increased performance."
                },
                {
                    "title": "Catalytic Exhaust Compatibility",
                    "content": "Compatible with catalytic exhaust systems, ensuring efficient operation in vehicles with such systems."
                },
                {
                    "title": "Smooth Clutch Performance",
                    "content": "Ensures smooth clutch operation, allowing for better power transfer to the wheels."
                },
                {
                    "title": "Fuel Consumption Reduction",
                    "content": "Potentially reduces fuel consumption by optimizing oil viscosity, benefiting fuel efficiency."
                },
                {
                    "title": "Cleaner Engine at Extreme Conditions",
                    "content": "Keeps engine components clean from harmful deposits, even under extreme operating conditions."
                },
                {
                    "title": "Reduced Maintenance and Operating Costs",
                    "content": "Reduces maintenance and operating costs by providing excellent wear protection to engine parts and gears."
                }
            ]
        };
    },
}
</script>
<style scoped>
.accordion-button:not(.collapsed) {
    color: #0d6efd;
    background-color: white;
}
</style>