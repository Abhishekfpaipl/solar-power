<template>
    <div class="container">
        <div class="text-start mb-5">
            <p class="text-muted mb-1 text-uppercase">Our</p>
            <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);"> Success Story</h2>
        </div>
        <div class="row mt-5">
            <div class="col-12 position-relative  d-flex align-items-center justify-content-center pt-5">
                <div class="card rounded-3">
                    <div class="image rounded-3">
                        <img href="#" :src="image" class="rounded-3" alt="Card image">
                    </div>
                    <div class="content">
                        <h3 class="mt-4 pt-2">{{ title }}</h3>
                        <p v-if="post" class="text-ellipsis2">{{ post }}</p>
                    </div>
                </div>
            </div>
            <div class="col-12 mt-5 text-center">
                CLG Oil India Private Limited embarked on its journey over two and a half decades ago, in 2000, making
                its mark by introducing high-quality greases for both automotive and industrial applications. These
                products are marketed under various leading brands, earning the company a strong reputation in the
                industry.
                Over the years, CLG Oil has grown into one of the foremost grease manufacturers in India, with a
                production capacity ranging between 2,200 to 2,700 MT per month. This impressive output meets more than
                15-20% of India's demand for premium greases, underscoring the company’s pivotal role in the market.
                In addition to greases, CLG Oil India Private Limited has diversified its product range to Lubricants
                and oils also, such as engine oils and industrial oils, catering to the automotive and industrial
                sectors both within India and internationally. The company's ability to evolve and expand its offerings
                has been a key factor in its sustained growth and success.
                Since its inception in 2000, CLG Oil India Private Limited has witnessed tremendous growth, establishing
                itself as a leading manufacturer and supplier of a comprehensive range of greases and lubricant oils.
                The company’s expertise lies in producing a wide array of products, including automotive greases,
                high-end lubricant oils, and synthetic oils, among others. Through continuous research and a strong
                focus on customer satisfaction, CLG Oil has remained attuned to the evolving demands of the modern
                Indian automotive industry, while also making significant strides in the domestic market. The company
                prides itself on delivering high-performance products that ensure 100% customer satisfaction, thereby
                maintaining its esteemed reputation for quality.
                The journey of CLG Oil India Private Limited began modestly in 1988, with operations starting in a small
                factory located in Bawana, Delhi. Fueled by relentless hard work, passion, and determination, the
                company steadily progressed, eventually rebranding as CLG Oil India Pvt Ltd in 2019. This transformation
                marked a new chapter in the company’s history, reflecting its growth and evolution over the years.
                At the helm of this successful venture is Mr. Vipin Goyal Sir, who has been the driving force behind the
                company's remarkable achievements. Under his leadership, CLG Oil India has reached unprecedented heights
                over the past three decades, thanks to his unparalleled work ethic and visionary approach. Joining him
                in this exceptional journey is his son, Mr. Gaurav Goyal, whose modern perspectives and enthusiasm have
                further amplified the company’s potential for success. Together, they have propelled CLG Oil India
                Private Limited to new levels of excellence, ensuring its continued prominence in the industry.
                We also offer private label grease & lubricants manufacturing to well recognized brands in the
                automotive aftermarket, MRO, and general industrial categories and independent marketing companies
                across the globe. We, at CLG Oil India Private Limited.
                In the year 2020, we aims to invest substantially in Research &Development, acquiring modern
                technologies and geographical expansion.

            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        tests: Array
    },
    data() {
        return {
            image: 'img/about/owner.jpeg',
            title: "Gaurav Goyal",
            post: "Owner"
        }
    }

};
</script>

<style scoped>
.card {
    position: relative;
    max-width: 300px;
    height: 215px;
    background-color: #fff;
    padding: 30px 15px;
    display: flex;
    flex-direction: column;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5);
    transition: 0.3s ease-in-out;
}

.card:hover {
    height: 265px;
}

.image {
    position: relative;
    width: 230px;
    min-height: 230px;
    top: -40%;
    left: 0px;
    box-shadow: 0 5px 20px rgba(0, 0, 0, 0.2);
    z-index: 1;
}

.image img {
    max-width: 100%;
    border-radius: 15px;
}

.content {
    position: relative;
    top: -140px;
    padding: 10px 15px;
    color: #111;
    text-align: center;
    visibility: hidden;
    opacity: 0;
    transition: 0.3s ease-in-out;
}

.card:hover .content {
    margin-top: 30px;
    visibility: visible;
    opacity: 1;
    transition-delay: 0.2s;
}
</style>