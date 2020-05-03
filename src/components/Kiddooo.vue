<template>
    <section class='kiddooo' id='kiddooo'>
        <div class='center_box'>
            <img class='phone' src='images/kiddooo.png' />
            <div class='description'>
                <h4>
                    Kiddooo App
                </h4>
                <p>
                    Keeping nannies, babysitters, parents & co-parents in 
                    the loop together, even when they're apart.
                </p>
                <h6>
                    Currently in development using Figma, Vue.js, Node.js, Express.js, MongoDB, and Cordova.
                </h6>
                <div class='tech_grid'>
                    <div v-for='icon in tech' :key='icon' class='icon'>
                        <img :src="'images/' + icon + '.png'" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'Kiddooo',
    components: {
        
    },
    data() {
        return {
            tech: [
                'figma',
                'vuejs',
                'nodejs',
                'express',
                'mongodb',
                'cordova'
            ]
        }
    },
    methods: {
    }
}
</script>

<style scoped lang="scss">
section.kiddooo {
    background-color: #eeeeee;
    display: flex;
    div.center_box {
        margin: auto;
        width: 660px;
        height: 552px;
        display: grid;
        grid-template-columns: 268px 345px;
        grid-column-gap: 47px;
        img.phone {
            display: block;
            width: 268px;
            height: 552px;
        }
        div.description {
            width: 345px;
            height: 552px;
            text-align: left;
            h4 {
                font-family: Comfortaa, sans-serif;
                font-weight: 400;
                font-size: 36px;
                line-height: 52px;
                margin: 60px 0 5px 0;
                padding: 0;
            }
            p {
                font-family: Comfortaa, sans-serif;
                font-weight: 400;
                font-size: 18px;
                line-height: 27px;
                margin: 0;
                padding: 0;
            }
            h6 {
                font-family: Comfortaa, sans-serif;
                font-weight: 100;
                font-size: 14px;
                line-height: 21px;
                margin: 12px 0 0 0;
                padding: 0;
            }
            div.tech_grid {
                width: 268px;
                height: 165px;
                margin-top: 88px;
                display: grid;
                grid-template-columns: 1fr 1fr;
                div.icon {
                    width: 134px;
                    height: 55px;
                    position: relative;
                    img {
                        max-width: 100px;
                        max-height: 40px;
                        position: absolute;
                        left: 0;
                        top: 50%;
                        transform: translateY(-50%);
                    }
                }
            }
        }
    }
}

</style>
