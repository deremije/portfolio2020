<template>
    <header>
        <div @click='toggle_logo' class='name'>
            jeremy / randall
        </div>
        <div class='logo_container' v-if='show.logo' @click='open_menu'> 
            <button class='orange' :class='open' ref='orange' @click='display_view("AboutMe")'>
                <span v-if='show_menu'>About Me</span>
            </button>
            <button class='green' :class='open' ref='green' @click='display_view("Technology")'>
                <span v-if='show_menu'>Tech & Skills</span>
            </button>
            <button class='blue' :class='open' ref='work_samples' @click='display_view("WorkSamples")'>
                <span v-if='show_menu'>Work Samples</span>
            </button>
            <button class='pink' :class='open' ref='pink' @click='display_view("Contact")'>
                <span v-if='show_menu'>Contact</span>
            </button>
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
header {
    height: 60px;
    line-height: 60px;
    padding: 10px 40px;
    width: calc(100vw - 80px);
    background-color: #e1e1e1;
    display: flex;
    justify-content: flex-start;
    .name {
        font-family: Raleway, sans-serif;
        font-size: 28px;
        text-align: left;
        cursor: pointer;
    }
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
        button {
            border: none;
            font-family: 'Comfortaa', cursive;
            font-size: 18px;
            text-align: center;
            line-height: 40px;
            font-weight: bold;
            cursor: pointer;
            span {
                animation: fade_into_view 200ms ease-in 600ms 1 both;
                transition: all 50ms linear;
            }
        }
        button:hover {
            span {
                color: #e4e4e4;
                text-shadow: 2px 2px #1a1a1a;
            }
        }
        .orange {
            width: 200px;
            height: 40px;
            left: calc(100vw - 330px - 875px);
            position: absolute;
            background-color: rgba(202,140,47,.79);
            transform: translateX(calc(-1 * (100vw - 330px - 796px))) translateY(-13px) scaleX(calc(40.25 / 200)) scaleY(calc(16.35 / 40)) ;
            transition: transform 400ms linear 600ms;
        }
        .green {
            width: 200px;
            height: 40px;
            position: absolute;
            left: calc(100vw - 330px - 650px);
            background-color: rgba(162,202,47,.80);
            transform: translateX(calc(-1 * (100vw - 330px - 610px))) translateY(-9.5px) scaleX(calc(32.4 / 200)) scaleY(calc(9.3 / 40));
            transition: transform 400ms linear 400ms;
        }
        .blue {
            width: 200px;
            height: 40px;
            position: absolute;
            left: calc(100vw - 330px - 425px);
            background-color: rgba(47,165,202,.50);
            transform: translateX(calc(-1 * (100vw - 330px - 394px))) translateY(7px) scaleX(calc(50.4 / 200)) scaleY(calc(18.45 / 40));
            transition: transform 400ms linear 200ms;
        }
        .pink {
            width: 200px;
            height: 40px;
            position: absolute;
            left: calc(100vw - 330px - 200px);
            background-color: rgb(211,89,213,.75);
            transform: translateX(calc(-1 * (100vw - 330px - 129.5px))) translateY(3.5px) scaleX(calc(22.95 / 200)) scaleY(calc(11.85 / 40));
            transition: transform 400ms linear;
        }
        .open {
            transform: none;
        }
    }
}
</style>
