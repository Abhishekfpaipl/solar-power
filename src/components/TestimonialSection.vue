<template>
    <div class="container my-5 text-dark">
        <div class="text-start mb-5">
            <p class="text-muted mb-1 text-uppercase">Review</p>
            <div class="d-md-flex justify-content-between align-items-center">
                <h2 class="display-5 text-uppercase" style="color: var(--bg-primary);">What our customers say about us
                </h2>
                <router-link to="/testimonial" class="position-absolute end-0 text-decoration-none pe-md-5 pe-1"
                    style="color: var(--bg-primary);">
                    See All <i class="bi bi-arrow-right"></i>
                </router-link>
            </div>
        </div>


        <article :class="['wrapper', { 'wrapper--vertical': isVertical }]" class="pb-5">
            <div class="marquee" :class="{ 'marquee--vertical': isVertical }">
                <div class="marquee__group mt-5" :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards" :key="index">
                        <div class="card-container bg-light border position-relative rounded p-2 ">
                            <div class="card border-0">
                                <div class="card-header d-flex flex-column justify-content-center align-items-center">
                                    <div class="rounded-circle overflow-hidden border border-white bg-light border-2 p-1"
                                        style="width:60px; height:60px; margin-top:-40px;">
                                        <img :src="card.image" alt="Profile" class="rounded-circle"
                                            style="width: 100%; height: 100%;object-fit: cover;" />
                                    </div>
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.title }}</p>
                                </div>
                                <div class="card-body bg-white py-2 px-1" style="max-width: 250px;">
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.name }}</p>
                                    <!-- <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.subtitle }}</p> -->
                                    <p class="text-dark smaller mb-0 text-ellipsis3">{{ card.review }} </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div aria-hidden="true" class="marquee__group mt-5"
                    :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards" :key="index">
                        <div class="card-container bg-light border position-relative rounded p-2 ">
                            <div class="card border-0">
                                <div class="card-header d-flex flex-column justify-content-center align-items-center">
                                    <div class="rounded-circle overflow-hidden border border-white bg-light border-2 p-1"
                                        style="width:60px; height:60px; margin-top:-40px;">
                                        <img :src="card.image" alt="Profile" class="rounded-circle"
                                            style="width: 100%; height: 100%;object-fit: cover;" />
                                    </div>
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.title }}</p>
                                </div>
                                <div class="card-body bg-white py-2 px-1" style="max-width: 250px;">
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.name }}</p>
                                    <!-- <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.subtitle }}</p> -->
                                    <p class="text-dark smaller mb-0 text-ellipsis3">{{ card.review }} </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="marquee marquee--reverse" :class="{ 'marquee--vertical': isVertical }">
                <div class="marquee__group mt-5" :style="{ 'animation-direction': isReverse ? 'normal' : 'reverse' }">
                    <div class="" v-for="(card, index) in cards2" :key="index">
                        <div class="card-container bg-light border position-relative rounded p-2 ">
                            <div class="card border-0">
                                <div class="card-header d-flex flex-column justify-content-center align-items-center">
                                    <div class="rounded-circle overflow-hidden border border-white bg-light border-2 p-1"
                                        style="width:60px; height:60px; margin-top:-40px;">
                                        <img :src="card.image" alt="Profile" class="rounded-circle"
                                            style="width: 100%; height: 100%;object-fit: cover;" />
                                    </div>
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.title }}</p>
                                </div>
                                <div class="card-body bg-white py-2 px-1" style="max-width: 250px;">
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.name }}</p>
                                    <!-- <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.subtitle }}</p> -->
                                    <p class="text-dark smaller mb-0 text-ellipsis3">{{ card.review }} </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div aria-hidden="true" class="marquee__group mt-5"
                    :style="{ 'animation-direction': isReverse ? 'normal' : 'reverse' }">
                    <div class="" v-for="(card, index) in cards2" :key="index">
                        <div class="card-container bg-light border position-relative rounded p-2 ">
                            <div class="card border-0">
                                <div class="card-header d-flex flex-column justify-content-center align-items-center">
                                    <div class="rounded-circle overflow-hidden border border-white bg-light border-2 p-1"
                                        style="width:60px; height:60px; margin-top:-40px;">
                                        <img :src="card.image" alt="Profile" class="rounded-circle"
                                            style="width: 100%; height: 100%;object-fit: cover;" />
                                    </div>
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.title }}</p>
                                </div>
                                <div class="card-body bg-white py-2 px-1" style="max-width: 250px;">
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.name }}</p>
                                    <!-- <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.subtitle }}</p> -->
                                    <p class="text-dark smaller mb-0 text-ellipsis3">{{ card.review }} </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="marquee" :class="{ 'marquee--vertical': isVertical }">
                <div class="marquee__group mt-5" :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards3" :key="index">
                        <div class="card-container bg-light border position-relative rounded p-2 ">
                            <div class="card border-0">
                                <div class="card-header d-flex flex-column justify-content-center align-items-center">
                                    <div class="rounded-circle overflow-hidden border border-white bg-light border-2 p-1"
                                        style="width:60px; height:60px; margin-top:-40px;">
                                        <img :src="card.image" alt="Profile" class="rounded-circle"
                                            style="width: 100%; height: 100%;object-fit: cover;" />
                                    </div>
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.title }}</p>
                                </div>
                                <div class="card-body bg-white py-2 px-1" style="max-width: 250px;">
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.name }}</p>
                                    <!-- <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.subtitle }}</p> -->
                                    <p class="text-dark smaller mb-0 text-ellipsis3">{{ card.review }} </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div aria-hidden="true" class="marquee__group mt-5"
                    :style="{ 'animation-direction': isReverse ? 'reverse' : 'normal' }">
                    <div class="" v-for="(card, index) in cards3" :key="index">
                        <div class="card-container bg-light border position-relative rounded p-2 ">
                            <div class="card border-0">
                                <div class="card-header d-flex flex-column justify-content-center align-items-center">
                                    <div class="rounded-circle overflow-hidden border border-white bg-light border-2 p-1"
                                        style="width:60px; height:60px; margin-top:-40px;">
                                        <img :src="card.image" alt="Profile" class="rounded-circle"
                                            style="width: 100%; height: 100%;object-fit: cover;" />
                                    </div>
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.title }}</p>
                                </div>
                                <div class="card-body bg-white py-2 px-1" style="max-width: 250px;">
                                    <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.name }}</p>
                                    <!-- <p class="fw-bold smaller mb-0 mt-0 text-ellipsis1">{{ card.subtitle }}</p> -->
                                    <p class="text-dark smaller mb-0 text-ellipsis3">{{ card.review }} </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </article>
    </div>
</template>

<script>

export default {
    name: "AutoScrolling",
    props: {
        brandColorOne: {
            type: String,
            default: '#000'
        }
    },
    data() {
        return {
            isVertical: false,
            isReverse: false,
            cards: [
                {
                    image: 'img/flags/usa.svg',
                    title: 'USA',
                    name: 'John Doe',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'The motor oil significantly improved the efficiency of our fleet. We saw a notable reduction in engine wear and tear. Highly recommended for heavy-duty vehicles.',
                },
                {
                    image: 'img/flags/canada.svg',
                    title: 'Canada',
                    name: 'Emily Johnson',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'After switching to this motor oil, our trucks run smoother and maintenance costs have dropped. It’s the best oil we’ve used so far.',
                },
                {
                    image: 'img/flags/uk.svg',
                    title: 'UK',
                    name: 'Michael Smith',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'This oil offers superior engine protection, even in extreme weather conditions. Our vehicles have been running efficiently across all terrains.',
                },
                {
                    image: 'img/flags/australia.jpg',
                    title: 'Australia',
                    name: 'Sarah Williams',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'Since we started using this motor oil, the performance consistency of our machinery has been remarkable. Fuel consumption has decreased as well.',
                },
                {
                    image: 'img/flags/germany.svg',
                    title: 'Germany',
                    name: 'David Brown',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'Our industrial machines are running more efficiently with less frequent oil changes. This motor oil truly maximizes engine longevity.',
                },
                {
                    image: 'img/flags/france.jpg',
                    title: 'France',
                    name: 'Sophia Martin',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'Exceptional quality! The motor oil keeps our engines running like new, even under heavy load. It’s a trusted part of our maintenance routine.',
                },
                {
                    image: 'img/flags/japan.svg',
                    title: 'Japan',
                    name: 'Hiroshi Yamamoto',
                    subtitle: 'Director at RBB Buildcon Pvt. Ltd.',
                    review: 'This motor oil provides excellent protection and enhances engine performance. We have seen extended service intervals and improved fuel efficiency.',
                },

            ],
            cards2: [
                {
                    image: 'img/flags/brazil.jpg',
                    title: 'Brazil',
                    name: 'Carlos Silva',
                    subtitle: 'Operations Manager at Tranporte Nacional',
                    review: 'Using this oil, we’ve noticed smoother engine operation in our transport fleet, even in high-heat conditions. Definitely a product we trust.',
                },
                {
                    image: 'img/flags/italy.jpg',
                    title: 'Italy',
                    name: 'Giulia Rossi',
                    subtitle: 'Fleet Supervisor at Milano Logistics',
                    review: 'The oil’s performance has been outstanding. Our trucks experience less downtime and run more efficiently on long routes.',
                },
                {
                    image: 'img/flags/south-korea.jpg',
                    title: 'South Korea',
                    name: 'Jung-ho Park',
                    subtitle: 'Technical Manager at Seoul Heavy Industries',
                    review: 'Our heavy-duty machinery runs like a dream with this oil. Its durability and protection have reduced wear and extended maintenance intervals.',
                },
                {
                    image: 'img/flags/russia.jpg',
                    title: 'Russia',
                    name: 'Anastasia Ivanova',
                    subtitle: 'Director at Siberian Transport Co.',
                    review: 'Even in sub-zero temperatures, this motor oil ensures reliable starts and optimal performance. It’s a game-changer for our operations.',
                },
                {
                    image: 'img/flags/mexico.svg',
                    title: 'Mexico',
                    name: 'Juan Lopez',
                    subtitle: 'Fleet Manager at Logística del Sur',
                    review: 'Since we began using this motor oil, our fuel consumption has noticeably decreased, and engine performance has never been better.',
                },
                {
                    image: 'img/flags/spain.svg',
                    title: 'Spain',
                    name: 'Isabella García',
                    subtitle: 'Logistics Coordinator at Transporte Ibérico',
                    review: 'Our fleet’s performance has greatly improved with this oil. The engines run smoother and require less frequent maintenance.',
                },
                {
                    image: 'img/flags/south-africa.jpg',
                    title: 'South Africa',
                    name: 'Thabo Mokoena',
                    subtitle: 'Operations Director at Cape Haulers',
                    review: 'This motor oil has proven to be reliable under extreme conditions. It keeps our engines performing at peak efficiency, even in hot climates.',
                }
            ],
            cards3: [
                {
                    image: 'img/flags/sweden.jpg',
                    title: 'Sweden',
                    name: 'Lars Johansson',
                    subtitle: 'Transport Manager at NordFreight AB',
                    review: 'The cold weather performance is exceptional. Even in freezing temperatures, the engines start smoothly, and we have had fewer breakdowns.',
                },
                {
                    image: 'img/flags/netherlands.jpg',
                    title: 'Netherlands',
                    name: 'Marieke Van Dijk',
                    subtitle: 'Fleet Manager at EuroTrans BV',
                    review: 'Since switching to this motor oil, our fleet has been more efficient, and we’ve noticed extended oil change intervals, saving both time and money.',
                },
                {
                    image: 'img/flags/argentina.jpg',
                    title: 'Argentina',
                    name: 'Diego Perez',
                    subtitle: 'Operations Lead at Andes Logistics',
                    review: 'We operate across different terrains, and this motor oil has ensured smooth performance, reducing engine wear in our trucks.',
                },
                {
                    image: 'img/flags/china.jpg',
                    title: 'China',
                    name: 'Li Wei',
                    subtitle: 'Maintenance Director at Beijing Freight Co.',
                    review: 'The oil’s longevity and efficiency have dramatically decreased our operational costs. It’s ideal for our high-performance fleet.',
                },
                {
                    image: 'img/flags/saudi-arabia.jpg',
                    title: 'Saudi Arabia',
                    name: 'Ahmed Al-Farouq',
                    subtitle: 'Logistics Head at Desert Transport Co.',
                    review: 'This oil stands up to the harsh desert environment, providing excellent performance even in extreme heat and sandy conditions.',
                },
                {
                    image: 'img/flags/norway.jpg',
                    title: 'Norway',
                    name: 'Erik Hansen',
                    subtitle: 'Fleet Supervisor at FjordHaulage AS',
                    review: 'Our trucks operate in challenging weather conditions, and this motor oil has provided consistent performance and protection all year round.',
                },
                {
                    image: 'img/flags/new-zealand.jpg',
                    title: 'New Zealand',
                    name: 'Olivia Clarke',
                    subtitle: 'Transport Director at Kiwi Logistics Ltd.',
                    review: 'The fuel efficiency and engine protection we’ve experienced with this oil are unmatched. It’s now a key part of our fleet’s maintenance.',
                }

            ]



        };
    },
    methods: {
        toggleDirection() {
            this.isVertical = !this.isVertical;
            this.isReverse = !this.isReverse;
        },
    },
};
</script>

<style>
:root {
    --color-text: navy;
    --color-bg: papayawhip;
    --color-bg-accent: #ecdcc0;
    --size: clamp(10rem, 1rem + 40vmin, 30rem);
    --gap: calc(var(--size) / 8);
    --duration: 20s;
    --scroll-start: 0;
    --scroll-end: calc(-100% - var(--gap));
}

.marquee {
    display: flex;
    overflow: hidden;
    user-select: none;
    gap: var(--gap);
    mask-image: linear-gradient(var(--mask-direction, to right),
            hsl(0 0% 0% / 0),
            hsl(0 0% 0% / 1) 20%,
            hsl(0 0% 0% / 1) 80%,
            hsl(0 0% 0% / 0));
}

.marquee__group {
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: space-around;
    gap: var(--gap);
    min-width: 100%;
    animation: scroll-x var(--duration) linear infinite;
}

@media (prefers-reduced-motion: reduce) {
    .marquee__group {
        animation-play-state: paused;
    }
}

.marquee--vertical {
    --mask-direction: to bottom;
}

.marquee--vertical,
.marquee--vertical .marquee__group {
    flex-direction: column;
}

.marquee--vertical .marquee__group {
    animation-name: scroll-y;
}

.marquee--reverse .marquee__group {
    animation-direction: reverse;
    animation-delay: -3s;
}

@keyframes scroll-x {
    from {
        transform: translateX(var(--scroll-start));
    }

    to {
        transform: translateX(var(--scroll-end));
    }
}

@keyframes scroll-y {
    from {
        transform: translateY(var(--scroll-start));
    }

    to {
        transform: translateY(var(--scroll-end));
    }
}

/* Parent wrapper */
.wrapper {
    display: flex;
    flex-direction: column;
    gap: var(--gap);
    margin: auto;
    max-width: 100vw;
}

.wrapper--vertical {
    flex-direction: row;
    height: 100vh;
}


@keyframes fade {
    to {
        opacity: 0;
        visibility: hidden;
    }
}

.card {
    height: 100%
}

.card-header {
    background: linear-gradient(180deg, rgba(255, 0, 0, 1) 0%, rgba(255, 255, 255, 1) 95%);
    ;
    padding: 10px;
    text-align: center;
    border-bottom: 0px !important;
}

.card-body {
    padding: 20px;
    text-align: center;
}

.card-container {
    min-width: 15rem !important
}

/* Quotation marks */
.card-container::before {
    content: '“';
    position: absolute;
    font-size: 2em;
    /* color: #4ecdc4; */
    color: white !important;
    font-family: sans-serif;
}

.card-container::after {
    content: '”';
    position: absolute;
    font-size: 2em;
    color: white !important;
    font-family: sans-serif;
}

.card-container::before {
    top: 0;
    left: -5px;
}

.card-container::after {
    bottom: -20px;
    right: -5px;
}
</style>