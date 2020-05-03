<template>
    <section>
        <transition name='fade_out'>
            <div class='gifs'>
                <div class='img_container' v-for='gif in gif_list' :key='gif' :class='gif'>
                    <img :src="'images/' + gif + '.gif'" class='image' />
                </div>
            </div>
        </transition>
    </section>
</template>

<script>
export default {
    name: 'AboutMe',
    data() {
        return {
            gif_list: [
                'lyon', 'teddy_kgb', 'austin', 'baby_spoon', 'balloons', 'good_place_killing_janet', 'hiking',
                'kip', 'orelsan_tout_va_bien', 'settlers', 'table_flip'
            ]
        }
    },
    methods: {
    }
}
</script>

<style scoped lang="scss">
.gifs {
    width: auto;
    height: calc(100vh - 160px);
    position: absolute;
    top: 0;
    left: 0;
    background-color: purple;
    .img_container {
        animation-duration: 10000ms;
        animation-timing-function: ease-in-out;
        animation-iteration-count: infinite;
        position: absolute;
        opacity: 0;
        // background-color: purple;
        .image {
            height: 100%;
            width: auto;
            position: absolute;
            top: 0%;
            left: 0%;
        }
    }
    .austin {
        top: 40vh;
        left: 5vw;
        width: 25vw;
        height: 40vh;
        animation-name: austin;
        animation-delay: 9s;
        @keyframes austin {
            10% {
                opacity: 1;
            }
            40% {
                opacity: 0;
            }
            100% {
                opacity: 0;
            }
        }
    }
    .baby_spoon {
        top: 45vh;
        left: 0;
        // width: 25vw;
        height: 30vh;
        animation-name: baby_spoon;
        animation-delay: 1s;
        @keyframes baby_spoon {
            0% {
                opacity: 1;
                transform: translate(-25vw, 0);
            }
            50% {
                transform: translate(110vw, 0);
            }
            100% {
                transform: translate(110vw, 0);
            }
        }
    }
    .balloons {
        top: 100vh;
        left: 60vw;
        width: 35vw;
        height: 65vh;
        width: auto;
        animation-name: balloons;
        animation-delay: 2s;
        @keyframes balloons {
            0% {
                opacity: 1;
                transform: translate(0, 0);
            }
            50% {
                transform: translate(0, -200vh);
                opacity: 0;
            }
            100% {
                transform: translate(0, -200vh);
                opacity: 0;
            }
        }
    }
    .good_place_killing_janet {
        top: 25vh;
        left: 0;
        width: 25vw;
        height: 30vh;
        animation-name: good_place_killing_janet;
        animation-delay: 3s;
        @keyframes good_place_killing_janet {
            0% {
                opacity: 1;
                transform: translate(-25vw, 0);
            }
            50% {
                transform: translate(110vw, 0);
            }
            100% {
                transform: translate(110vw, 0);
            }
        }
    }
    .hiking {
        top: 30vh;
        left: 0;
        width: 25vw;
        height: 35vh;
        animation-name: hiking;
        animation-delay: 4s;
        @keyframes hiking {
            0% {
                opacity: 1;
                transform: translate(110vw, 0);
            }
            50% {
                
                transform: translate(-35vw, 0);
            }
            100% {
                
                transform: translate(-35vw, 0);
            }
        }
    }
    .kip {
        top: 25vh;
        left: 0;
        width: 25vw;
        height: 50vh;
        animation-name: kip;
        animation-delay: 5s;
        @keyframes kip {
            0% {
                opacity: 1;
                transform: translate(-25vw, 0);
            }
            50% {
                transform: translate(110vw, 0);
            }
            100% {
                transform: translate(110vw, 0);
            }
        }
    }
    .lyon {
        top: 5vh;
        left: 50vw;
        width: 25vw;
        height: 22vw;
        animation-name: lyon;
        animation-delay: 6s;
        @keyframes lyon {
            10% {
                opacity: 1;
            }
            40% {
                opacity: 0;
            }
            100% {
                opacity: 0;
            }
        }
    }
    .orelsan_tout_va_bien {
        top: 35vh;
        left: 0;
        width: 25vw;
        height: 40vh;
        animation-name: orelsan_tout_va_bien;
        animation-delay: 7s;
        @keyframes orelsan_tout_va_bien {
            0% {
                opacity: 1;
                transform: translate(-35vw, 0);
            }
            50% {
                transform: translate(110vw, 0);
            }
            100% {
                transform: translate(110vw, 0);
            }
        }
    }
    .settlers {
        top: 20vh;
        left: 0;
        width: 25vw;
        height: 25vh;
        animation-name: settlers;
        animation-delay: 8s;
        @keyframes settlers {
            0% {
                opacity: 1;
                transform: translate(-25vw, 0);
            }
            50% {
                transform: translate(110vw, 0);
            }
            100% {
                transform: translate(110vw, 0);
            }
        }
    }
    .table_flip {
        top: 0;
        left: 0;
        width: 25vw;
        height: 45vh;
        animation-name: table_flip;
        animation-delay: 7s;
        @keyframes table_flip {
            0% {
                opacity: 1;
                transform: translate(125vw, 145vh);
            }
            50% {
                
                transform: translate(-25vw, -45vh);
            }
            100% {
                transform: translate(-25vw, -45vh);
            }
        }
    }
    .teddy_kgb {
        top: -45vh;
        left: 30vw;
        width: 25vw;
        height: 45vh;
        animation-name: teddy_kgb;
        animation-delay: 10s;
        @keyframes teddy_kgb {
            0% {
                opacity: 1;
                transform: translate(0, 0);
            }
            50% {
                transform: translate(0, 145vh);
            }
            100% {
                transform: translate(0, 145vh);
            }
        }
    }
}
.fade_out-enter,
.fade_out-leave-to {
    opacity: 0;
}
.fade_out-enter-active,
.fade_out-leave_active {
    transition: opacity 1s;
}
</style>
