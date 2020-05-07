<template>
    <div id="app">
        <Header :show='show'></Header>
        <Hero></Hero>
        <AboutMe></AboutMe>
        <Technology></Technology>
        <WorkSamples @add_scoop='add_scoop'></WorkSamples>
        <Kiddooo></Kiddooo>
        <Contact></Contact>
        
        <footer>
            <div>
                Copyright 2020 Jeremy Randall
            </div>
            <div class='social_icons'>
                <a href='https://www.linkedin.com/in/jeremy-randall-61217919/' target='_blank'>
                    <img src='images/linkedin.png' />
                </a>
                <a href='https://www.github.com/deremije' target='_blank'>
                    <img src='images/github.png' />
                </a>
                <a href='https://www.codepen.io/deremije' target='_blank'>
                    <img src='images/codepen.png' />
                </a>
                <a href='https://www.freecodecamp.org/%C4%91eremije' target='_blank'>
                    <img src='images/fcc.png' />
                </a>
            </div>
            <div>
                This Page is <a href='https://github.com/deremije/portfolio2020' target='_blank'>Open Source</a>
            </div>
            
        </footer>
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
    </div>
</template>

<script>
import Header from './components/Header.vue';
import AboutMe from './components/AboutMe.vue';
import Technology from './components/Technology.vue';
import WorkSamples from './components/WorkSamples.vue';
import Contact from './components/Contact.vue';
import Hero from './components/Hero.vue';
import Kiddooo from './components/Kiddooo.vue';

export default {
    name: 'App',
    components: {
        WorkSamples, Header, AboutMe, Technology, Contact, Hero, Kiddooo
    },
    data() {
        return {
            show_blank: true,
            show: {
                logo: true,
            },
            scoops: []
        }
    },
    computed: {
        open() {
            return this.show_menu ? 'open' : '';
        },
    },
    methods: {
        display_view(view) {
            this.active_view = view;
        },
        add_scoop(flavor) {
            this.scoops.push(flavor);
        }
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@500&family=Didact+Gothic&family=Raleway:wght@400;600&display=swap');

html {
    scroll-behavior: smooth;
}
html, body {
    margin: 0;
    padding: 0;
    width: 100vw;
    
}

#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    width: 100%;
    height: 100vh;
    overflow: auto;
    
    p {
        font-family: 'Didact Gothic', sans-serif;
        font-size: 18px;
    }
    a {
        text-decoration: none;
    }
    section {
        width: 100%;
            padding: 40px 0;
            height: auto;
        overflow: hidden;
        @media screen and (max-width: 1024px) {
        }
    }
    footer {
        font-family: Raleway, sans-serif;
        font-size: 18px;
        height: 60px;
        line-height: 60px;
        padding: 10px 40px;
        width: auto;
        background-color: #e1e1e1;
        transition: all 200ms linear;
        text-align: left;
        display: flex;
        justify-content: space-evenly;
        position: relative;
        div {
            width: 350px;
            text-align: center;
        }
        div.social_icons {
            display: flex;
            justify-content: center;
            img {
                height: 40px;
                width: auto;
                margin: 10px;
            }
        }
        @media screen and (max-width: 1049px) {
            div {
                width: 280px;
                font-size: 14px;
            }
        }
        @media screen and (max-width: 750px) {
            height: auto;
            padding: 20px calc(50% - 140px);
            margin: auto;
            width: 280px;
            text-align: center;
            flex-direction: column;
            div {
                width: 280px;
                height: 60px;
                font-size: 18px;
            }
        }
    }
    .ic_animation {
        position: fixed;
        right: 40px;
        bottom: 0px;
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
        @media screen and (max-width: 450px) {
            display: none;
        }
    }
    @keyframes fade_into_view {
        from { opacity: 0 }
        to { opacity: 1 }
    }
}
</style>
