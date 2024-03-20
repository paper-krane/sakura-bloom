<template>
    <section class="pk__small-text_section pk__section-margin-top pk__section-margin-bot">
        <div class="pk__container pk__m">
            <span class="pk__small-text_percent">100%</span>
            <p>We're really proud to say that everything we make is made in our studio in California. We keep a close eye on every step of how our baby carriers are made, from the very start to the finished product.</p>
        </div>
    </section>
</template>

<script setup>

</script>

<style lang="scss">
@import "@/assets/_variables";

.pk__small-text_section {
    text-align: center;

    .pk__small-text_percent {
        font-size: 7rem;
        font-family: $heading-font-stack;
        line-height: 1;
        color: lighten($font-color, 70%);
    }

    p {
        font-weight: 300;
    }

    @media #{$l-and-up} {
        p {
            font-size: 1.4vw;
        }
    }
}
</style>