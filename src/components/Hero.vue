<template>
    <div class='hero logo'>
        <div class='big_logo'>
            <div class='logo_create' ref='logo_create' :class='spin'>
                <div class='orange' ref='orange' @click='black'></div>
                <div class='green' ref='green' @click='turn'></div>
                <div class='pink' ref='pink' @click='shatter'></div>
                <div class='blue' ref='blue' @click='toggle_spin'></div>
            </div>
            <div class='big_text text_jeremy' ref='jeremy'>jeremy</div>
            <div class='big_text text_randall' ref='randall'>randall</div>
        </div>
    </div>
        
</template>

<script>
export default {
    name: 'Hero',
    data() {
        return {
            blue_spin: false
        }
    },
    computed: {
        spin() {
            return this.blue_spin ? 'spin' : ''; 
        }
    },
    methods: {
        add_scoop(flavor) {
            this.$emit("add_scoop", flavor);
        },
        black() {
            this.$refs.orange.classList.add('black');
            setTimeout(() => {
                this.$refs.orange.classList.remove('black');
            }, 1850);
            setTimeout(() => {
                this.$refs.blue.classList.add('black');
                setTimeout(() => {
                    this.$refs.blue.classList.remove('black');
                }, 1850);
            }, 150);
            setTimeout(() => {
                this.$refs.green.classList.add('black');
                setTimeout(() => {
                    this.$refs.green.classList.remove('black');
                }, 1850);
            }, 300);
            setTimeout(() => {
                this.$refs.pink.classList.add('black');
                setTimeout(() => {
                    this.$refs.pink.classList.remove('black');
                }, 1850);
            }, 450);
            setTimeout(() => {
                this.$refs.jeremy.classList.add('white');
                this.$refs.randall.classList.add('white');
                setTimeout(() => {
                    this.$refs.jeremy.classList.remove('white');
                    this.$refs.randall.classList.remove('white');
                }, 1250);
            }, 600);
        },
        shatter() {
            this.$refs.orange.classList.add('orange_shatter');
            setTimeout(() => {
                this.$refs.blue.classList.add('blue_shatter');
            }, 150);
            setTimeout(() => {
                this.$refs.green.classList.add('green_shatter');
            }, 300);
            setTimeout(() => {
                this.$refs.pink.classList.add('pink_shatter');
            }, 450);
            
            setTimeout(() => {
                this.blue_spin = false;
                this.reset_turns();
                this.$refs.orange.classList.remove('orange_shatter');
                this.$refs.blue.classList.remove('blue_shatter');
                this.$refs.pink.classList.remove('pink_shatter');
                this.$refs.green.classList.remove('green_shatter');
            }, 1500);
        },
        reset_turns() {
            this.$refs.green.classList.remove('turn');
            this.$refs.blue.classList.remove('turn');
            this.$refs.orange.classList.remove('turn');
            this.$refs.pink.classList.remove('turn');
        },
        turn() {
            if (this.$refs.green.classList.contains('turn')) {
                this.reset_turns();
            } else {
                this.$refs.green.classList.add('turn');
                this.$refs.blue.classList.add('turn');
                this.$refs.orange.classList.add('turn');
                this.$refs.pink.classList.add('turn');
            }
        },
        toggle_spin() {
            this.blue_spin = !this.blue_spin;
        }
    }
}
</script>

<style scoped lang="scss">
$orange: rgba(202,140,47,.79);
$green: rgba(162,202,47,.80);
$blue: rgba(47,165,202,.50);
$pink: rgb(211,89,213,.75);

.hero {
    width: 100%;
    --hero_height: 40vh;
    margin: 80px 0 0 0;
    @media screen and (max-width: 450px) {
        --hero_height: 20vh;
        margin: 0;
    }
    height: var(--hero_height);
    padding: 0;
    background-color: #EEEEEE;
    position: relative;
    display: flex;
    overflow: hidden;
    .big_logo {
        display: block;
        --logo_width: 30vw;
        @media screen and (max-width: 450px) {
            --logo_width: 60vw;
        }
        @media screen and (max-width: 450px) {
            --logo_width: 60vw;
        }
        width: calc(var(--logo_width));
        height: calc(var(--logo_width) * 244 / 616);
        margin: auto;
        position: relative;
        transition: transform 300ms linear;
        div.logo_create {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
            transition: transform 500ms ease-in;
            div {
                position: absolute;
                cursor: pointer;
                transition: transform 300ms ease, background-color 300ms linear;
            }
            div.orange {
                background-color: $orange;
                top: 0;
                left: 0;
                width: calc(100% * 269 / 616);
                height: calc(100% * 109 / 244);
            }
            div.green {
                background-color: $green;
                top: calc(100% * 47 / 244);
                left: calc(100% * 280 / 616);
                width: calc(100% * 216 / 616);
                height: calc(100% * 62 / 244);
            }
            div.blue {
                background-color: $blue;
                top: calc(100% * 120 / 244);
                left: calc(100% * 280 / 616);
                width: calc(100% * 336 / 616);
                height: calc(100% * 123 / 244);
            }
            div.pink {
                background-color: $pink;
                top: calc(100% * 120 / 244);
                left: calc(100% * 116 / 616);
                width: calc(100% * 153 / 616);
                height: calc(100% * 79 / 244);
            }
            div.black {
                background-color: #1a1a1a;
            }
            div.turn {
                transform: rotate(90deg);
            }
            div.orange_shatter {
                transform: translate(-600px, -200px);
            }
            div.blue_shatter {
                transform: translate(600px, 200px);
            }
            div.green_shatter {
                transform: translate(600px, -200px);
            }
            div.pink_shatter {
                transform: translate(-600px, 200px);
            }
        }
        .spin {
            transform: rotate(180deg);
        }
        img {
            display: block;
            position: relative;
            top: 0;
            height: auto;
            width: 100%;
        }
        .big_text {
            font-family: Raleway, sans-serif;
            font-size: calc(var(--logo_width) / 12);
            position: absolute;
            transition: color 300ms linear;
        }
        .text_randall {
            bottom: 1.5%;
            right: 2%;
        }
        .text_jeremy {
            top: 1.5%;
            left: 2%;
        }
        .white {
            color: #EEEEEE;
        }
    }
}

</style>
