<template>
    <section>
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
p {
    padding: 0px 0 5px;
    @media screen and (max-width: 450px) {
        width: calc(100% - 60px);
        height: auto;
        margin: 20px auto;
        padding: 0;
    }
}
.clickable {
    cursor: pointer;
    text-decoration: underline;
    font-weight: 600;
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

</style>
