<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { RouterLink } from 'vue-router';
import { ref, onMounted } from 'vue';

// Images
import image1 from '@/assets/images/image_008upscaled.webp';

// Ref's
const categoriesContainerRef = ref(null);
const ctx = ref(null);

// On Component Mount
onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);

    ctx.value = gsap.context(() => {
        gsap.set('.pk__categories_link-container', {
            y: 40,
            opacity: 0,
        });
        gsap.to('.pk__categories_link-container', {
            duration: 2.4,
            y: 0,
            opacity: 1,
            stagger: 0.15,
            ease: 'power4.out',
            scrollTrigger: {
                trigger: categoriesContainerRef.value,
                start: 'top 70%',
            },
        });
    });
});
</script>


<template>
    <section class="pk__categories_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__container" ref="categoriesContainerRef">
            <h4>Find your right fit...</h4>
            <RouterLink to="#" class="pk__categories_link-container">
                <div class="pk__categories_link-image">
                    <figure>
                        <img :src="image1" alt="" style="object-position: 75% 50%;" />
                    </figure>
                </div>
                <div class="pk__categories_link-content">
                    <h4>Scouts</h4>
                    <p>Designed to be worn on the front or the back and carry your little one from newborn stage through toddlerhood.</p>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__categories_link-container">
                <div class="pk__categories_link-image">
                    <figure>
                        <img src="//sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_300x.jpg?v=1675035897" srcset="//sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_180x.jpg?v=1675035897 180w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_360x.jpg?v=1675035897 360w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_540x.jpg?v=1675035897 540w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_720x.jpg?v=1675035897 720w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_900x.jpg?v=1675035897 900w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_1080x.jpg?v=1675035897 1080w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_1296x.jpg?v=1675035897 1296w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_1512x.jpg?v=1675035897 1512w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_1728x.jpg?v=1675035897 1728w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_1944x.jpg?v=1675035897 1944w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_2160x.jpg?v=1675035897 2160w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_2376x.jpg?v=1675035897 2376w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_2592x.jpg?v=1675035897 2592w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_2808x.jpg?v=1675035897 2808w, //sakurabloom.com/cdn/shop/files/DA803B47-427A-41C8-BB27-9344EC40576B_3024x.jpg?v=1675035897 3024w">
                    </figure>
                </div>
                <div class="pk__categories_link-content">
                    <h4>Onbuhimos</h4>
                    <p>A traditional Japanese style baby carrier designed to be worn high on the back, but can also be worn on the front.</p>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__categories_link-container">
                <div class="pk__categories_link-image">
                    <figure>
                        <img src="https://storageciggallery.addons.business/18193/cig-cozy-gallery-11474FXB-0622-Newport-Onbuhimos-9-xxl.jpg?c=00" alt="" />
                    </figure>
                </div>
                <div class="pk__categories_link-content">
                    <h4>Ring Slings</h4>
                    <p>A versatile carrier designed to be a custom-fit each time in a variety of different carry styles.</p>
                </div>
            </RouterLink>
        </div>
    </section>
</template>


<style lang="scss">
@import "@/assets/_variables";

.pk__categories_section {
    overflow: hidden;

    .pk__container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;

        &> h4 {
            grid-column: span 2;
            margin-bottom: 0;
            padding-bottom: 1rem;
        }

        .pk__categories_link-container,
        .pk__categories_link-container:visited {
            display: block;
            position: relative;
            overflow: hidden;
            text-decoration: none;
            color: $white;
            transition: none;

            .pk__categories_link-image {
                aspect-ratio: 3 / 4;
                position: relative;
                overflow: hidden;
                border-radius: $border-radius;
                background-color: darken($site-bg, 5%);

                figure {
                    margin: 0;
                    position: absolute;
                    top: 0;
                    left: 0;
                    width: 100%;
                    height: 100%;

                    img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                        object-position: 50% 50%;
                    }
                }
            }

            &:nth-child(2) {
                grid-column: span 2;
            }

            .pk__categories_link-content {
                padding: 1rem;
                background-color: transparent;
                border-radius: $border-radius;
                position: absolute;
                left: 0;
                bottom: 0;
                width: 100%;
                z-index: 1;
                backdrop-filter: blur(6px);
                -webkit-backdrop-filter: blur(6px);

                h4 {
                    font-size: 1.25rem;
                    margin-bottom: .5rem;
                }

                p {
                    display: none;
                }
            }
        }
    }

    @media #{$l-and-up} {
        .pk__container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 1rem;

            h4 {
                grid-column: span 3;
            }

            .pk__categories_link-container,
            .pk__categories_link-container:visited {
                display: grid;
                grid-template-columns: 120px 1fr;
                gap: 1rem;
                align-items: center;
                color: $font-color;
                border-radius: $border-radius;
                background-color: darken($site-bg, 4%);
                padding-right: 40px;

                &:nth-child(2) {
                    grid-column: span 1;
                }

                .pk__categories_link-image {
                    aspect-ratio: 2 / 3;
                    border-radius: $border-radius 0 0 $border-radius;

                    figure {
                        img {
                            transition: all 1s ease;
                        }
                    }
                }

                .pk__categories_link-content {
                    position: relative;
                    backdrop-filter: none;
                    -webkit-backdrop-filter: none;

                    p {
                        font-size: .875rem;
                        font-weight: 300;
                        display: block;
                        color: lighten($font-color, 40%);
                    }
                }
            }

            .pk__categories_link-container:hover,
            .pk__categories_link-container:focus {
                .pk__categories_link-image {
                    figure {
                        img {
                            transform: scale(1.1);
                        }
                    }
                }
            }
        }
    }

    @media #{$xl-and-up} {
        .pk__container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 2rem;

            .pk__categories_link-container {
                grid-template-columns: 200px 1fr;

                .pk__categories_link-image {
                    aspect-ratio: 3 / 4;
                }
            }
        }
    }
}
</style>