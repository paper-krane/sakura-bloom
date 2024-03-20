<script setup>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/all';
import { onMounted, onUnmounted, ref } from 'vue';
import { RouterLink } from 'vue-router';

// Components
import Link from '@/components/Link.vue';

// Ref's 
const featuredProductsSectionRef = ref(null);
const ctx = ref(null);

// On Component Mount
onMounted(() => {
    gsap.registerPlugin(ScrollTrigger);

    ctx.value = gsap.context(() => {
        gsap.set('.pk__featured-products_product-card', {
            opacity: 0,
            y: '40px'
        });
        gsap.to('.pk__featured-products_product-card', {
            duration: 2.4,
            opacity: 1,
            y: 0,
            stagger: 0.1,
            ease: 'power4.out',
            scrollTrigger: {
                trigger: featuredProductsSectionRef.value,
                start: 'top 80%',
            },
        });
    });
});

onUnmounted(() => {
    if (ctx.value) ctx.value.revert();
});
</script>


<template>
    <section ref="featuredProductsSectionRef" class="pk__featured-products_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__container pk__featured-products_heading">
            <h2>Featured Baby Carriers</h2>
            <Link
                href="#"
                size="sm"
            >
                View All
            </Link>
        </div>
        <div class="pk__container pk__featured-products_grid">
            <RouterLink to="#" class="pk__featured-products_product-card">
                <img 
                    src="https://sakurabloom.com/cdn/shop/files/CreamO-1_1080x.jpg?v=1702434374"
                    srcset="https://sakurabloom.com/cdn/shop/files/CreamO-1_360x.jpg?v=1702434374 360w, https://sakurabloom.com/cdn/shop/files/CreamO-1_540x.jpg?v=1702434374 540w, https://sakurabloom.com/cdn/shop/files/CreamO-1_720x.jpg?v=1702434374 720w, https://sakurabloom.com/cdn/shop/files/CreamO-1_900x.jpg?v=1702434374 900w, https://sakurabloom.com/cdn/shop/files/CreamO-1_1080x.jpg?v=1702434374 1080w"
                >
                <div class="pk__featured-products_product-card-details">
                    <h3>Bisque Onbuhimo</h3>
                    <span>$198.00</span>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__featured-products_product-card">
                <img 
                    src="//sakurabloom.com/cdn/shop/files/BluffOL_1of4_1080x.jpg?v=1702746502"
                    srcset="//sakurabloom.com/cdn/shop/files/BluffOL_1of4_360x.jpg?v=1702746502 360w, //sakurabloom.com/cdn/shop/files/BluffOL_1of4_540x.jpg?v=1702746502 540w, //sakurabloom.com/cdn/shop/files/BluffOL_1of4_720x.jpg?v=1702746502 720w, //sakurabloom.com/cdn/shop/files/BluffOL_1of4_900x.jpg?v=1702746502 900w, //sakurabloom.com/cdn/shop/files/BluffOL_1of4_1080x.jpg?v=1702746502 1080w"
                >
                <div class="pk__featured-products_product-card-details">
                    <h3>Bluff & Whiskey Leather Onbuhimo</h3>
                    <span>$340.00</span>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__featured-products_product-card">
                <img 
                    src="//sakurabloom.com/cdn/shop/files/ShadeRS-1_1080x.jpg?v=1706485749"
                    srcset="//sakurabloom.com/cdn/shop/files/ShadeRS-1_360x.jpg?v=1706485749 360w, //sakurabloom.com/cdn/shop/files/ShadeRS-1_540x.jpg?v=1706485749 540w, //sakurabloom.com/cdn/shop/files/ShadeRS-1_720x.jpg?v=1706485749 720w, //sakurabloom.com/cdn/shop/files/ShadeRS-1_900x.jpg?v=1706485749 900w, //sakurabloom.com/cdn/shop/files/ShadeRS-1_1080x.jpg?v=1706485749 1080w"
                >
                <div class="pk__featured-products_product-card-details">
                    <h3>Shade Ring Sling</h3>
                    <span>$220.00</span>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__featured-products_product-card">
                <img 
                    src="//sakurabloom.com/cdn/shop/files/SolsticeHoneyOL-1_1080x.jpg?v=1709667051"
                    srcset="//sakurabloom.com/cdn/shop/files/SolsticeHoneyOL-1_360x.jpg?v=1709667051 360w, //sakurabloom.com/cdn/shop/files/SolsticeHoneyOL-1_540x.jpg?v=1709667051 540w, //sakurabloom.com/cdn/shop/files/SolsticeHoneyOL-1_720x.jpg?v=1709667051 720w, //sakurabloom.com/cdn/shop/files/SolsticeHoneyOL-1_900x.jpg?v=1709667051 900w, //sakurabloom.com/cdn/shop/files/SolsticeHoneyOL-1_1080x.jpg?v=1709667051 1080w"
                >
                <div class="pk__featured-products_product-card-details">
                    <h3>Solstice & Honey Leath Onbuhimo</h3>
                    <span>$440.00</span>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__featured-products_product-card">
                <img 
                    src="//sakurabloom.com/cdn/shop/files/JetS-1_1080x.jpg?v=1698886204"
                    srcset="//sakurabloom.com/cdn/shop/files/JetS-1_360x.jpg?v=1698886204 360w, //sakurabloom.com/cdn/shop/files/JetS-1_540x.jpg?v=1698886204 540w, //sakurabloom.com/cdn/shop/files/JetS-1_720x.jpg?v=1698886204 720w, //sakurabloom.com/cdn/shop/files/JetS-1_900x.jpg?v=1698886204 900w, //sakurabloom.com/cdn/shop/files/JetS-1_1080x.jpg?v=1698886204 1080w"
                >
                <div class="pk__featured-products_product-card-details">
                    <h3>Bisque Onbuhimo</h3>
                    <span></span>
                </div>
            </RouterLink>
            <RouterLink to="#" class="pk__featured-products_product-card">
                <img
                    src="//sakurabloom.com/cdn/shop/files/ToffeeRS_3of3_1080x.jpg?v=1695595593" 
                    srcset="//sakurabloom.com/cdn/shop/files/ToffeeRS_3of3_360x.jpg?v=1695595593 360w, //sakurabloom.com/cdn/shop/files/ToffeeRS_3of3_540x.jpg?v=1695595593 540w, //sakurabloom.com/cdn/shop/files/ToffeeRS_3of3_720x.jpg?v=1695595593 720w, //sakurabloom.com/cdn/shop/files/ToffeeRS_3of3_900x.jpg?v=1695595593 900w, //sakurabloom.com/cdn/shop/files/ToffeeRS_3of3_1080x.jpg?v=1695595593 1080w"
                >
                <div class="pk__featured-products_product-card-details">
                    <h3>Bisque Onbuhimo</h3>
                    <span></span>
                </div>
            </RouterLink>
        </div>
    </section>
</template>


<style lang="scss" scoped>
@import "@/assets/_variables";

.pk__featured-products_section {
    overflow: hidden;

    .pk__featured-products_heading {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 40px;

        h2 {
            text-transform: uppercase;
            font-size: .75rem;
            letter-spacing: .125rem;
            font-family: $font-stack;
            color: lighten($font-color, 40%);
            margin-bottom: 0;
        }
    }

    .pk__featured-products_grid {
        display: flex;
        flex-wrap: nowrap;

        .pk__featured-products_product-card {
            display: block;
            width: 66%;
            flex: none;
            text-decoration: none;
            color: lighten($font-color, 40%);
            transition: none;

            .pk__featured-products_product-card-details {
                padding-top: 20px;
                padding-left: 20px;
                padding-right: 20px;
                text-align: center;

                h3 {
                    font-size: .875rem;
                    text-transform: uppercase;
                    letter-spacing: .125rem;
                    margin-bottom: .25rem;
                    font-family: $font-stack;
                    overflow: hidden;
                    white-space: nowrap;
                    text-overflow: ellipsis;
                }

                span {
                    font-size: .875rem;
                }
            }
        }
    }

    @media #{$m-and-up} {
        .pk__featured-products_grid {
            .pk__featured-products_product-card {
                width: 30%;
            }
        }
    }

    @media #{$l-and-up} {
        .pk__featured-products_grid {
            .pk__featured-products_product-card {
                width: 24%;
            }
        }
    }
}
</style>