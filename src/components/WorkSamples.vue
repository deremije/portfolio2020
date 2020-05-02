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
        <p>
            Getting to use <span class='clickable' @click='add_scoop("mint")'>Vue.js</span> is like adding <span class='clickable' @click='add_scoop("mint")'>Mint</span>
        </p>
        <div class='ic_animation'>
            <div class='ice_cream'>
                <div class='scoops'>
                    <div v-for='scoop in scoops'>
                        <div class='ball' :class='scoop'></div>
                        <div class='squish' :class='scoop'></div>
                    </div>
                </div>
                <div class='cone' v-if='scoops.length > 0'></div>
            </div>
        </div>
    </section>
        
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
            scoops: []
        }
    },
    methods: {
        add_scoop(flavor) {
            this.scoops.push(flavor);
        }
    }
}
</script>

<style scoped lang="scss">
p {
    padding: 0px 0 5px;
}
.clickable {
    cursor: pointer;
    text-decoration: underline;
    font-weight: 600;
}
.slider {
    margin: 0 auto 140px;
}
.tech_logos {
    display: block;
    margin: auto;
    height: 60px;
    width: auto;
}
.ic_animation {
    position: fixed;
    right: 40px;
    bottom: 80px;
    height: 100vw;
    width: 40px;
    .ice_cream {
        width: 40px;
        height: auto;
        position: absolute;
        bottom: 0;
        margin: auto;
        .scoops {
            display: flex;
            flex-direction: column-reverse;
        }
        .ball {
            border-radius: 50%;
            width: 40px;
            height: 40px;
            margin-top: -10px;
            animation: scoop 1s linear;
            box-shadow: 2px 0px #1a1a1a55;
        }
        .squish {
            width: 40px;
            height: 10px;
            border-radius: 30px;
            border-bottom: solid 1px #1a1a1a55;
            margin-top: -10px;
            animation: scoop 1s linear;
            box-shadow: 2px 0px #1a1a1a55, 0px -1px #3f3f3f55;
        }
        .chocolate,
        .strawberry,
        .vanilla,
        .mint {
            position: relative;
            opacity: 1;
        }
        .chocolate {
            background-color: #6b3e26;
        }
        .strawberry {
            background-color: #ffc5d9;
        }
        .vanilla {
            background-color: #fdf5c9;
        }
        .mint {
            background-color: #c2f2d0;
        }
        .cone {
            border-top: solid 80px tan;
            border-right: solid 20px transparent;
            border-left: solid 20px transparent;
            width: 0px;
            height: 0px;
            opacity: 1;
            animation: cone 900ms linear 0s 1 both;
            box-shadow: 0px -1px #1a1a1a55;
        }
        @keyframes cone {
            0% {
                opacity: 0;
                transform: translateX(-100vw);
            }
            1% {
                opacity: 1;
            }
            100% {
                opacity: 1;
                transform: translateX(0);
            }
        }
        @keyframes scoop {
            0% {
                opacity: 1;
                transform: translateY(-100vh);
            }
            100% {
                transform: translateY(0);
            }
        }
        @keyframes rise {
            from {
                transform: translateY(0);
            }
            to {
                transform: translateY(-200vh);
            }
        }
    }
}
</style>
