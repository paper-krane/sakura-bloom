<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';
import { RouterLink } from 'vue-router';
import { ref, onMounted, onUnmounted } from 'vue';

// Ref's 
const linkGridRef = ref(null);
const image1Ref = ref(null);
const image2Ref = ref(null);
const image3Ref = ref(null);
const image4Ref = ref(null);
const ctx = ref(null);

onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);

    const images = [image1Ref.value, image2Ref.value, image3Ref.value, image4Ref.value];

    gsap.to(images, {
        scrollTrigger: {
            trigger: linkGridRef.value,
            scrub: true
        },
        y: '20vh',
        ease: 'linear'
    });

    gsap.from('.pk__link-grid_swipe-reveal', {
        scrollTrigger: {
            trigger: linkGridRef.value
        },
        width: 'calc(100% + 2px)',
        ease: 'power4.inOut',
        duration: 1.4
    })
})
</script>


<template>
    <section class="pk__link-grid_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__container pk__link-grid_container" ref="linkGridRef">
            <RouterLink to="#" class="pk__link-grid_link">
                <div class="pk__link-grid_link-image-wrap">
                    <figure class="pk__link-grid_link-image" ref="image1Ref">
                        <img src="https://cdn.shopify.com/s/files/1/0925/6396/files/sakurabloom-5184_2048x2048.jpg?v=1529046241" alt="Link Image">
                    </figure>
                </div>
                <div class="pk__link-grid_link-content">
                    <h5>About Us</h5>
                </div>
                <div class="pk__link-grid_swipe-reveal"></div>
            </RouterLink>
            <RouterLink to="#" class="pk__link-grid_link">
                <div class="pk__link-grid_link-image-wrap">
                    <figure class="pk__link-grid_link-image" ref="image2Ref">
                        <img src="https://storageciggallery.addons.business/18193/cig-cozy-gallery-114749Vv-0622-Newport-Onbuhimos-3-hd.jpg?c=00" alt="Link Image">
                    </figure>
                </div>
                <div class="pk__link-grid_link-content">
                    <h5>Care & Maintenance</h5>
                </div>
                <div class="pk__link-grid_swipe-reveal"></div>
            </RouterLink>
            <RouterLink to="#" class="pk__link-grid_link">
                <div class="pk__link-grid_link-image-wrap">
                    <figure class="pk__link-grid_link-image" ref="image3Ref">
                        <img src="https://sakurabloom.com/cdn/shop/files/eyelet_leather_thumbnail_website.jpg?v=1674188265" alt="Link Image">
                    </figure>
                </div>
                <div class="pk__link-grid_link-content">
                    <h5>Journal</h5>
                </div>
                <div class="pk__link-grid_swipe-reveal"></div>
            </RouterLink>
            <RouterLink to="#" class="pk__link-grid_link">
                <div class="pk__link-grid_link-image-wrap">
                    <figure class="pk__link-grid_link-image" ref="image4Ref">
                        <img src="https://storageciggallery.addons.business/18193/cig-cozy-gallery-114747Ve-0622-Newport-Onbuhimos-22-hd.jpg?c=00" alt="Link Image">
                    </figure>
                </div>
                <div class="pk__link-grid_link-content">
                    <h5>Shop</h5>
                </div>
                <div class="pk__link-grid_swipe-reveal"></div>
            </RouterLink>
        </div>
    </section>
</template>


<style lang="scss">
@import "@/assets/_variables";

.pk__link-grid_section {
    .pk__link-grid_container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;

        .pk__link-grid_link {
            position: relative;

            .pk__link-grid_swipe-reveal {
                position: absolute;
                bottom: -1px;
                right: -1px;
                width: 0;
                height: calc(100% + 2px);
                background-color: $site-bg;
                pointer-events: none;
            }

            &:first-child,
            &:nth-child(2) {
                grid-column: span 2;
            }

            &:nth-child(2) {
                .pk__link-grid_link-image-wrap {
                    aspect-ratio: 2 / 1;
                }
            }

            &:nth-child(4) {
                .pk__link-grid_link-image-wrap {
                    figure {
                        img {
                            object-position: left top;
                        }
                    }
                }
            }

            .pk__link-grid_link-image-wrap {
                overflow: hidden;
                border-radius: 0.5rem;
                aspect-ratio: 1 / 1;
                position: relative;

                figure {
                    position: absolute;
                    bottom: 0;
                    left: 0;
                    width: 100%;
                    height: calc(100% + 20vh);
                    margin: 0;
                    padding: 0;

                    img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                        object-position: center;
                    }
                }
            }

            .pk__link-grid_link-content {
                padding: 1rem;
                position: absolute;
                bottom: 0;
                left: 0;
                width: 100%;

                h5 {
                    color: $white;
                    display: inline-block;
                    backdrop-filter: blur(6px);
                    -webkit-backdrop-filter: blur(6px);
                    background-color: rgba($font-color, .1);
                    border-radius: $border-radius;
                    padding-top: .25rem;
                    padding-bottom: .25rem;
                    padding-left: 1.5rem;
                    padding-right: 1.5rem;
                    margin-bottom: 0;
                }
            }
        }
    }

    @media #{$l-and-up} {
        .pk__link-grid_container {
            grid-template-columns: repeat(4, 1fr);
            gap: 40px;
            align-items: stretch;

            .pk__link-grid_link,
            .pk__link-grid_link:visited {
                transition: all .6s ease;

                &:first-child {
                    grid-row: span 2;

                    .pk__link-grid_link-image-wrap {
                        aspect-ratio: auto;
                        position: absolute;
                        top: 0;
                        left: 0;
                        width: 100%;
                        height: 100%;
                    }
                }
            }

            .pk__link-grid_link:hover, 
            .pk__link-grid_link:active {
                transform: scale(.975);
            }
        }
    }
}
</style>