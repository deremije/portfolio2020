<template>
    <section class='work_samples'>
        <div class='marker' id='work_samples'></div>
        <SiteSlider class='slider' @scoop='add_scoop'></SiteSlider>
        <p>
            I hand-crank simple websites for individuals and small businesses like ice cream:
        </p>
        <p>
            <span class='clickable' @click='add_scoop("chocolate")'>Chocolate HTML</span>,
            <span class='clickable' @click='add_scoop("strawberry")'>Strawberry CSS</span>, and
            <span class='clickable' @click='add_scoop("vanilla")'>Vanilla JavaScript</span>
        </p>
    </section>
</template>

<script>
import SiteSlider from './SiteSlider.vue';

export default {
    name: 'WorkSamples',
    components: {
        SiteSlider
    },
    methods: {
        add_scoop(flavor) {
            this.$emit("add_scoop", flavor);
        }
    }
}
</script>

<style scoped lang="scss">
section.work_samples {
    position: relative;
    background-color: #f3f3f3;
    .marker {
        width: 100%;
        height: 0px;
        top: 0px;
        position: absolute;
    }

    p {
        padding: 0px 0 5px;
        @media screen and (max-width: 649px) {
            width: 450px;
            margin: auto;
        }
        @media screen and (max-width: 470px) {
            width: 280px;
            height: auto;
            margin: 20px auto;
            padding: 0;
        }
    }
    .clickable {
        cursor: pointer;
        text-decoration: underline;
        font-weight: 600;
        @media screen and (max-width: 470px) {
            cursor: default;
            text-decoration: none;
            font-weight: 400;
        }
    }
    .slider {
        margin: 50px auto 140px;
    }
    .tech_logos {
        display: block;
        margin: auto;
        height: 60px;
        width: auto;
    }
}
</style>
