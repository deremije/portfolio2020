<template>
    <header>
        <div @click='toggle_logo' class='name'>
            jeremy / randall
        </div>
        <div class='logo_container' v-if='show.logo' @click='open_menu'> 
            <a href='#about_me'>
                <button class='orange' :class='open' ref='orange'>
                    <span v-if='show_menu'>About Me</span>
                </button>
            </a>
            <a href='#technology'>
                <button class='green' :class='open' ref='green'>
                    <span v-if='show_menu'>Tech & Skills</span>
                </button>
            </a>
            <a href='#work_samples'>
                <button class='blue' :class='open' ref='work_samples'>
                    <span v-if='show_menu'>Previous Work</span>
                </button>
            </a>
            <a href='#contact'>
                <button class='pink' :class='open' ref='pink' @click='display_view("Contact")'>
                    <span v-if='show_menu'>Contact</span>
                </button>
            </a>
        </div>
    </header>
</template>

<script>

export default {
    name: 'Header',
    props: {
        show: Object
    },
    data() {
        return {
            show_menu: false,
        }
    },
    mounted() {
        setTimeout(() => {
            this.open_menu();
        }, 600);
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
        toggle_logo() {
            this.show_menu = false;
            this.$emit("display_view", "blank");
            setTimeout(() => {
                this.open_menu();
            }, 1400);
        },
        display_view(view) {
            if (this.show_menu) this.$emit("display_view", view);
        },
    }
}
</script>

<style scoped lang="scss">
$orange: rgba(202,140,47,.79);
$green: rgba(162,202,47,.80);
$blue: rgba(47,165,202,.50);
$pink: rgb(211,89,213,.75);

header {
    height: 60px;
    line-height: 60px;
    padding: 10px 40px;
    width: calc(100vw - 80px);
    background-color: #e1e1e1;
    display: flex;
    justify-content: flex-start;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 60;
    @media screen and (max-width: 450px) {
        display: none;
        position: relative;
    }
    .name {
        font-family: Raleway, sans-serif;
        font-size: 28px;
        text-align: left;
        cursor: pointer;
        @media screen and (max-width: 450px) {
            text-align: center;
        }
    }
    .logo_container {
        display: block;
        height: 40px;
        width: calc(100vw - 330px);
        position: absolute;
        top: 20px;
        left: 280px;
        animation: fade_into_view 300ms ease-in 0s 1 forwards;
        button {
            border: none;
            text-align: center;
            position: absolute;
            width: 200px;
            height: 40px;
            line-height: 40px;
            font-family: 'Comfortaa', cursive;
            font-size: 18px;
            font-weight: bold;
            color: #1a1a1a;
            cursor: pointer;
            text-shadow: 1px 1px transparent;
            span {
                animation: fade_into_view 200ms ease-in 600ms 1 both;
                transition: all 50ms linear;
            }
        }
        button:hover {
            span {
                text-shadow: 1px 1px #e1e1e1;
            }
        }
        .orange {
            left: calc(100vw - 330px - 875px);
            background-color: $orange;
            transform: translateX(calc(-1 * (100vw - 330px - 796px))) translateY(-13px) scaleX(calc(40.25 / 200)) scaleY(calc(16.35 / 40)) ;
            transition: transform 400ms linear 600ms;
        }
        .green {
            left: calc(100vw - 330px - 650px);
            background-color: $green;
            transform: translateX(calc(-1 * (100vw - 330px - 610px))) translateY(-9.5px) scaleX(calc(32.4 / 200)) scaleY(calc(9.3 / 40));
            transition: transform 400ms linear 400ms;
        }
        .blue {
            left: calc(100vw - 330px - 425px);
            background-color: $blue;
            transform: translateX(calc(-1 * (100vw - 330px - 394px))) translateY(7px) scaleX(calc(50.4 / 200)) scaleY(calc(18.45 / 40));
            transition: transform 400ms linear 200ms;
        }
        .pink {
            left: calc(100vw - 330px - 200px);
            background-color: $pink;
            transform: translateX(calc(-1 * (100vw - 330px - 129.5px))) translateY(3.5px) scaleX(calc(22.95 / 200)) scaleY(calc(11.85 / 40));
            transition: transform 400ms linear;
        }
        .open {
            transform: none;
        }
        @media screen and (max-width: 1210px) {
            width: calc(100vw - 530px);
            button {
                width: 150px;
            }
            .orange {
                left: calc(100vw - 330px - 675px);
            }   
            .green {
                left: calc(100vw - 330px - 500px);
            }
            .blue {
                left: calc(100vw - 330px - 325px);
            }
            .pink {
                left: calc(100vw - 330px - 150px);
            } 
        }
        @media screen and (max-width: 1010px) {
            width: calc(100vw - 760px);
            button {
                width: 100px;
                font-size: 12px;
            }
            .orange {
                left: calc(100vw - 330px - 445px);
            }   
            .green {
                left: calc(100vw - 330px - 330px);
            }
            .blue {
                left: calc(100vw - 330px - 215px);
            }
            .pink {
                left: calc(100vw - 330px - 100px);
            } 
        }
        @media screen and (max-width: 768px) {
            display: none;
        }
    }
}
</style>
