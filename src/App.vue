<template>
    <div id="app">
        <header>
            <div>
                jeremy / randall
            </div>
            <div class='logo_container' v-if='show_logo' @click='open_menu'> 
                <button class='orange' :class='open' ref='orange' @click='menu_show("orange")'>
                    <span v-if='show_menu'>About Me</span>
                </button>
                <button class='green' :class='open' ref='green' @click='menu_show("green")'>
                    <span v-if='show_menu'>Applications</span>
                </button>
                <button class='blue' :class='open' ref='blue' @click='menu_show("websites")'>
                    <span v-if='show_menu'>Websites</span>
                </button>
                <button class='pink' :class='open' ref='pink' @click='menu_show("pink")'>
                    <span v-if='show_menu'>Contact</span>
                </button>
            </div>
        </header>
        <section class='blank' v-if='show_blank'>
            <img src='images/logo.svg' ref='big_logo' @click='zoom_blue'/>
        </section>
        <section v-if='show.websites'>
            <h2>
                Small Business & Individual Websites
            </h2>
            <SiteSlider class='center'></SiteSlider>
            <!-- <img src='images/logo.svg' class='logo_main' /> -->
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
        </section>
        <footer>
            <div>
                Copyright 2020 Jeremy Randall
            </div>

        </footer>
    </div>
</template>

<script>
import SiteSlider from './components/SiteSlider.vue'

export default {
    name: 'App',
    components: {
        SiteSlider
    },
    data() {
        return {
            show_menu: false,
            show_logo: false,
            show_blank: true,
            show: {
                websites: false
            }
        }
    },
    computed: {
        open() {
            return this.show_menu ? 'open' : '';
        },
    },
    methods: {
        open_menu() {
            this.show_menu = true;
        },
        menu_show(color) {
            // something
            this.show[color] = true;
        },
        zoom_blue() {
            this.$refs.big_logo.classList.add('zoom_blue');
            
            setTimeout(() => {
                this.show_blank = false;
            }, 1200);
            
            setTimeout(() => {
                this.show_logo = false;
                this.$nextTick(() => {
                    this.show_logo = true;
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
    .center {
        margin: auto;
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
        padding: 10px 0;
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
    header {
        font-family: Raleway, sans-serif;
        font-size: 28px;
        height: 60px;
        line-height: 60px;
        padding: 10px 40px;
        width: calc(100vw - 80px);
        background-color: #e1e1e1;
        transition: all 200ms linear;
        text-align: left;
        display: flex;
        justify-content: flex-start;
        .logo_container {
            display: block;
            grid-template-columns: 40.35px 50.4px;
            grid-template-rows: 16.35px 18.45px;
            grid-gap: 1.65px;
            height: 40px;
            margin-top: 10px;
            width: calc(100vw - 330px);
            animation: fade_into_view 300ms ease-in 0s 1 forwards;
            position: absolute;
            top: 10px;
            left: 280px;
            transition: all 400ms linear;
            button {
                border: none;
                font-family: 'Comfortaa', cursive;
                font-size: 18px;
                text-align: center;
                line-height: 40px;
                font-weight: bold;
                cursor: pointer;
            }
            .orange {
                width: 200px;
                height: 40px;
                left: calc(100vw - 330px - 875px);
                position: absolute;
                background-color: rgba(202,140,47,.79);
                transform: translateX(calc(-1 * (100vw - 330px - 796px))) translateY(-5px) scaleX(calc(40.25 / 200)) scaleY(calc(16.35 / 40)) ;
                transition: all 400ms linear 600ms;
            }
            .green {
                width: 200px;
                height: 40px;
                position: absolute;
                left: calc(100vw - 330px - 650px);
                background-color: rgba(162,202,47,.80);
                transform: translateX(calc(-1 * (100vw - 330px - 610px))) translateY(-1.5px) scaleX(calc(32.4 / 200)) scaleY(calc(9.3 / 40));
                transition: all 400ms linear 400ms;
            }
            .blue {
                width: 200px;
                height: 40px;
                position: absolute;
                left: calc(100vw - 330px - 425px);
                background-color: rgba(47,165,202,.50);
                transform: translateX(calc(-1 * (100vw - 330px - 394px))) translateY(15px) scaleX(calc(50.4 / 200)) scaleY(calc(18.45 / 40));
                transition: all 400ms linear 200ms;
            }
            .pink {
                width: 200px;
                height: 40px;
                position: absolute;
                left: calc(100vw - 330px - 200px);
                background-color: rgb(211,89,213);
                transform: translateX(calc(-1 * (100vw - 330px - 129.5px))) translateY(11.5px) scaleX(calc(22.95 / 200)) scaleY(calc(11.85 / 40));
                transition: all 400ms linear;
            }
            .open {
                transform: none;
            }
        }
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
    .blank {
        width: 100%;
        height: calc(100vh - 80px);
        overflow: hidden;
        padding: 0;
        margin: 0;
        display: flex;
        background-color: #e1e1e1;
        img {
            display: block;
            height: 40%;
            width: auto;
            margin: auto;
            transform: translateX(5%);
        }
    }
    .site_slider {
        position: relative;
        top: -15%;
        margin-bottom: 40px;
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
            animation: rise 10s linear 10.5s 1 both;
            .ball {
                border-radius: 50%;
                width: 40px;
                height: 40px;
                margin-top: -10px;
            }
            .squish {
                width: 40px;
                height: 10px;
                border-radius: 30px;
                margin-top: -10px;
            }
            .chocolate {
                background-color: brown;
                position: relative;
                z-index: 10;
                opacity: 1;
                animation: scoop 4000ms linear 6s 1 both;
            }
            .strawberry {
                background-color: pink;
                position: relative;
                z-index: 20;
                opacity: 1;
                animation: scoop 5000ms linear 6s 1 both;
            }
            .vanilla {
                background-color: #ddd;
                position: relative;
                z-index: 30;
                opacity: 1;
                animation: scoop 6000ms linear 6s 1 both;
            }
            .cone {
                border-top: solid 80px tan;
                border-right: solid 20px transparent;
                border-left: solid 20px transparent;
                width: 0px;
                height: 0px;
                opacity: 1;
                animation: cone 3000ms linear 6.75s 1 both;
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
                    transform: translateY(-4000px);
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
