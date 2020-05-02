<template>
    <div id="app">
        <Header :show='show' @display_view='display_view'></Header>
        <section class='logo' :class='active_view'>
            <div class='big_logo'>
                <img src='images/logo.svg' />
                <div class='big_text text_work_samples'>Work Samples</div>
                <div class='big_text text_jeremy'>jeremy</div>
                <div class='big_text text_randall'>randall</div>
            </div>
        </section>

        <component :is='active_view' class='center_position'></component>
        <!-- <section v-if='show.websites'>
            <h2>
                Small Business & Individual Websites
            </h2>
            <SiteSlider class='center'></SiteSlider>
            <p>
                I hand-crank simple websites for individuals and small businesses like ice cream:
            </p>
            <p>
                Chocolate HTML, Strawberry CSS, and Vanilla JavaScript
            </p>
            <div class='ic_animation'>
                <div class='ice_cream'>
                    <div class='ball vanilla'></div>
                    <div class='squish vanilla'></div>
                    <div class='ball strawberry'></div>
                    <div class='squish strawberry'></div>
                    <div class='ball chocolate'></div>
                    <div class='squish chocolate'></div>
                    <div class='cone'></div>
                </div>
            </div>
        </section> -->
        <footer>
            <div>
                Copyright 2020 Jeremy Randall
            </div>
        </footer>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import AboutMe from './components/AboutMe.vue';
import Technology from './components/Technology.vue';
import WorkSamples from './components/WorkSamples.vue';
import Contact from './components/Contact.vue';

export default {
    name: 'App',
    components: {
        WorkSamples, Header, AboutMe, Technology, Contact
    },
    data() {
        return {
            active_view: 'blank',
            show_blank: true,
            show: {
                logo: true,
            },
            
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
        zoom() {
            this.$refs.big_logo.classList.add('zoom_blue');
            
            setTimeout(() => {
                this.show_blank = false;
            }, 1200);
            
            setTimeout(() => {
                this.show.logo = false;
                this.$nextTick(() => {
                    this.show.logo = true;
                })
            }, 2300)
        }
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@500&family=Didact+Gothic&family=Raleway:wght@400;600&display=swap');

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
    overflow: hidden;
    .center_position {
        top: 80px;
        left: 0;
        position: absolute;
        background-color: transparent;
    }
    h2 {
        text-align: left;
        padding: 0 calc(50% - 750px);
        font-size: 24px;
        font-family: 'Comfortaa', cursive;
    }
    p {
        font-family: 'Didact Gothic', sans-serif;
        font-size: 18px;
    }
    a {
        text-decoration: none;
    }
    .logo_main {
        display: block;
        height: 40px;
        width: auto;
        margin: auto;
        padding: 30px 0 20px;
    }
    section {
        width: 100%;
        height: calc(100vh - 240px);
        overflow: auto;
        padding: 40px 0;
        background-color: #f3f3f3;
        animation: fade_into_view 300ms ease-in 0s 1 forwards;
        -ms-overflow-style: none; // IE
        scrollbar-width: none;  // FF
    }
    section::-webkit-scrollbar { // CHROME
        display: none;
    }
    .logo {
        width: 100%;
        height: calc(100vh - 160px);
        overflow: hidden;
        padding: 0;
        margin: 0;
        background-color: #f0f0f0;
        position: relative;
        display: flex;
        .big_logo {
            display: block;
            height: auto;
            width: 50%;
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
            .big_text {
                font-size: 56px;
                font-family: Comfortaa, sans-serif;
                color: #1a1a1a;
            }
            .text_work_samples {
                position: absolute;
                bottom: 17%;
                right: 4%;
                transform: scale(-1);
                opacity: 0;
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
    .blank {
        .big_logo {
            .text_randall,
            .text_jeremy {
                opacity: 1;
                transition: opacity 200ms linear 400ms;
            }
        }
    }
    .WorkSamples {
        .big_logo {
            transform: translate(-55%, -65%) scale(.7) rotate(180deg);
            img {
                opacity: .7;
                transition: opacity 200ms ease-in;
            }
            .text_work_samples {
                opacity: 1;
                transition: opacity 200ms linear 400ms;
            }
        }
    }
    footer {
        font-family: Raleway, sans-serif;
        font-size: 18px;
        height: 60px;
        line-height: 60px;
        padding: 10px 40px;
        width: calc(100vw - 80px);
        background-color: #e1e1e1;
        transition: all 200ms linear;
        text-align: left;
        display: flex;
        justify-content: center;
        position: fixed;
        bottom: 0;
    }
    
    @keyframes fade_into_view {
        from { opacity: 0 }
        to { opacity: 1 }
    }
    .zoom_blue {
        animation: zoom_blue 2s ease-in 0s 1 forwards;
        @keyframes zoom_blue {
            0% {
                opacity: 1;
            }
            70% {
                opacity: 1;
            }
            100% {
                opacity: 0;
                transform: scale(100) translateY(-10%); 
            }
        }
    }
}
</style>
