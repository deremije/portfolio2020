<template>
    <section class='about_me'>
        <div class='marker' id='about_me'></div>
        <div class='center_box'>
            <h2 v-if='show_french'>
                Bonjour,<br />
                je m'appelle Jeremy
            </h2>
            <h2 v-else>Hi, I'm Jeremy</h2>
            <img src='images/jeremy.png' alt="Jeremy having a beer in Zagreb, Croatia" />
            <div v-if='show_french'>
                <p>
                    Je suis un développeur <span @click='show_french = false'>américain</span> d'UI d'Austin, Texas, qui travaille maintenant depuis mon domicile à Lyon. Je recherche des problèmes intéressants qui nécessitent des solutions innovantes.
                </p>
                <p>
                    Je suis disponible pour les petits ou les grands contrats.
                </p>
                <p>
                    Dites-moi comment je peux vous aider.
                </p>
            </div>
            <div v-else>
                <p>
                    I'm an American UI developer from Austin, Texas now working remotely from my home in <span @click='show_french = true'>Lyon, France</span>. I seek out interesting problems in need of innovative solutions.
                </p>
                <p>
                    I am available for contracts ranging in length from one day to several years.
                </p>
                <p>
                    Let me know how I can help you.
                </p>
            </div>
        </div>
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
            ],
            show_french: false
        }
    },
    computed: {
        french() {
            return this.show_french ? 'french' : '';
        }
    },
    methods: {
    }
}
</script>

<style scoped lang="scss">
section.about_me {
    background-color: #F3F3F3;
    display: flex;
    height: auto;
    position: relative;
    .marker {
        width: 100%;
        height: 0px;
        top: -80px;
        position: absolute;
    }
    div.center_box {
        margin: auto;
        width: 932px;
        height: auto;
        min-height: 405px;
        display: grid;
        grid-template-columns: 1fr 405px;
        grid-template-rows: 90px; 
        grid-column-gap: 65px;
        h2 {
            grid-column: 1;
            font-family: Raleway, sans-serif;
            font-size: 48px;
            font-weight: 300;
            padding: 0 0 42px 0;
            margin: 0;
            text-align: left;
        }
        img {
            width: 405px;
            height: 392px;
            border-radius: 5px;
            grid-column: 2;
        }
        p {
            grid-column: 1;
            width: 425px;
            font-family: Comfortaa, sans-serif;
            font-size: 20px;
            line-height: 30px;
            margin: 0;
            padding: 24px 0 0 0;
            text-align: left;
        }
        span {
            cursor: pointer;
        }
        @media screen and (max-width: 1012px) {
            width: 680px;
            grid-template-columns: 1fr 260px;
            min-height: 260px;
            h2 {
                font-size: 36px;
            }
            img {
                width: 100%;
                height: auto;
            }
            p {
                width: 100%;
            }
        }
        @media screen and (max-width: 767px) {
            width: 280px;
            display: block;
            padding: 40px 0;
        }
    }
    
}
</style>
