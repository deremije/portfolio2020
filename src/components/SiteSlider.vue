<template>
    <div class='site_slider'>
        <div class='window' v-for='site in sites' :key='site.site' :class='site.class' @click='bring_to_front(site.site)'>
            <img v-if='screen_width > 450' :src='"images/" + site.site + ".png"' :alt="site.link" />
            <img v-else :src='"images/" + site.site + "_320.png"' :alt="site.link" />
        </div>
        <div class='link' v-if='show_link'>
            <a :href="'https://' + front_slide.link">
                {{ front_slide.link }}
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'SiteSlider',
    data() {
        return {
            show_link: true,
            sites: { 
                cryptomnio: { 
                    site: 'cryptomnio',
                    class: 'front',
                    description: 'Landing page for a cryptocurrency exchange aggregator and trading tool. Whipped up in a day from a pencil sketch.',
                    link: 'cryptomnio.com',
                    flavor: 'chocolate'
                }, 
                shannon: {
                    site: 'shannon',
                    class: 'second',
                    description: 'Portfolio site for a UX/UI Designer.  Single Page reactive app built in vanilla HTML / CSS / JS.',
                    link: 'shannou.com',
                    flavor: 'vanilla'
                }, 
                donnelly: {
                    site: 'donnelly',
                    class: 'third',
                    description: 'Small business brochure site for an accountant serving Americans living in France.',
                    link: 'donnelly-cpa.com',
                    flavor: 'strawberry'
                },
            },
        }
    },
    computed: {
        front_slide() {
            for (let site in this.sites) {
                if (this.sites[site].class == 'front') {
                    return this.sites[site];
                }
            }
        },
        screen_width() {
            return window.screen.width;
        }
    },
    methods: {
        bring_to_front(site_name) {
            if (this.sites[site_name].class != 'front') {
                this.$emit("scoop", this.sites[site_name].flavor);
                for (let site in this.sites) {
                    if (this.sites[site].class == 'front') {
                        this.sites[site].class = this.sites[site_name].class;
                    }
                }
                this.sites[site_name].class = 'front';
                this.show_link = false;
                setTimeout(() => {
                    this.show_link = true;
                }, 600)
            }
        },
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$image_tall: 420px;
$animation_ms: 600ms;

.site_slider {
    --image_wide: 800px;
    --image_tall: 420px;
    @media screen and (max-width: 1210px) {
        --image_wide: 600px;
        --image_tall: 315px;
    }
    @media screen and (max-width: 920px) {
        --image_wide: 360px;
        --image_tall: 190px;
    }
    @media screen and (max-width: 580px) {
        --image_wide: 240px;
        --image_tall: 130px;
    }
    @media screen and (max-width: 450px) {
        --image_wide: 240px;
        --image_tall: 422px;
    }
    position: relative;
    width: var(--image_wide);
    height: var(--image_tall);
    padding: 20px 0;
    margin-bottom: 40px;
    .window {
        width: calc(100% - 2px);
        height: calc(100% - 2px);
        border-radius: 3px;
        margin: auto;
        overflow-x: hidden;
        overflow-y: auto;
        transition: all linear $animation_ms;
        position: absolute;
        bottom: 0;
        left: 0;
        transform-origin: top right;
        -ms-overflow-style: none; // IE
        scrollbar-width: none;  // FF
        img {
            width: 100%;
            height: auto;
        }
    }
    .window::-webkit-scrollbar { // CHROME
        display: none;
    }
    .front {
        transform: scale(1) translate(0, calc(var(--image_tall) / 4));
        z-index: 40;
        opacity: 1;
        border: solid 1px #DDDDDD44;
    }
    .second {
        transform: scale(.85) translate(calc(var(--image_wide) / 6), calc(var(--image_tall) / 8));
        z-index: 30;
        opacity: .8;
        cursor: pointer;
    }
    .third {
        transform: scale(.7) translate(calc(var(--image_wide) / 3), 0px);
        z-index: 20;
        opacity: .6;
        cursor: pointer;
    }
    .fourth {
        transform: scale(.55) translate(calc(var(--image_wide) / 1.8), calc(var(--image_tall) / -8));
        z-index: 10;
        opacity: .4;
        cursor: pointer;
    }
    .link {
        color: white;
        text-shadow: 2px 2px black;
        font-size: 18px;
        line-height: 20px;
        font-family: 'Didact Gothic', serif;
        padding: 10px 20px;
        border: none;
        position: absolute;
        bottom: 0;
        transform: translateY(calc(var(--image_tall) / 4));
        right: 0;
        background-color: #00000044;
        z-index: 40;
        animation: fade_inward 300ms linear;
        @keyframes fade_inward {
            0% {
                opacity: 0;
            }
            100% {
                opacity: 1;
            }
        }
        a {
            color: white;
            text-shadow: 2px 2px black;
        }
    }
}
</style>
