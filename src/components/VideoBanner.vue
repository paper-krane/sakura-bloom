<script setup>

</script>


<template>
    <section class="pk__video-banner_section pk__section-margnin-top pk__section-margnin-bot pk__section-padding-top pk__section-padding-bot">
        <div class="pk__video-banner_video">
            <video autoplay muted loop playsinline>
                <source src="https://cdn.shopify.com/videos/c/o/v/6c89f37abd3c43aaa07a6c073fafa652.mp4" type="video/mp4">
            </video>
        </div>
    </section>
</template>


<style lang="scss">
@import "@/assets/_variables";

.pk__video-banner_section {
    position: relative;
    height: 65svh;
    background-color: $font-color;

    .pk__video-banner_video {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;

        video {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
            opacity: .65;
            filter: contrast(1.75) brightness(80%);
            -webkit-filter: contrast(1.25) brightness(80%);
        }
    }
}
</style>