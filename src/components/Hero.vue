<template>
    <div class='hero logo'>
        <div class='big_logo'>
            <img src='images/logo.svg' />
            <div class='big_text text_jeremy'>jeremy</div>
            <div class='big_text text_randall'>randall</div>
        </div>
    </div>
        
</template>

<script>
import SiteSlider from './SiteSlider.vue';

export default {
    name: 'WorkSamples',
    components: {
        SiteSlider
    },
    data() {
        return {
            
        }
    },
    methods: {
        add_scoop(flavor) {
            this.$emit("add_scoop", flavor);
        }
    }
}
</script>

<style scoped lang="scss">
.hero {
    width: 100%;
    height: 40vh;
    padding: 80px 0 0 0;
    margin: 0;
    background-color: #EEEEEE;
    position: relative;
    display: flex;
    .big_logo {
        display: block;
        height: auto;
        width: auto;
        height: calc(20vh - 80px);
        margin: auto;
        position: relative;
        transition: transform 300ms linear;
        img {
            display: block;
            position: relative;
            top: 0;
            width: 100%;
            height: auto;
        }
        .text_randall {
            font-family: Raleway, sans-serif;
            position: absolute;
            bottom: 1.5%;
            right: 2%;
            opacity: 0;
        }
        .text_jeremy {
            font-family: Raleway, sans-serif;
            position: absolute;
            top: 1.5%;
            left: 2%;
            opacity: 0;
        }
    }
}

</style>
