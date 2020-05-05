<template>
    <section class='kiddooo' id='kiddooo'>
        <div class='center_box'>
            <div class='description'>
                <h4>
                    Kiddooo App
                </h4>
                <p>
                    Keeping nannies, babysitters, parents & co-parents in 
                    the loop together, even when they're apart.
                </p>
            </div>
            <img class='phone' src='images/kiddooo.png' />
            <div class='devtools'>
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
        grid-template-rows: 216px 1fr;
        grid-column-gap: 47px;
        img.phone {
            display: block;
            width: 268px;
            height: 552px;
            grid-column: 1 / span 1;
            grid-row: 1 / span 2;
        }
        div.description {
            width: 345px;
            height: auto;
            text-align: left;
            grid-column: 2 / span 1;
            grid-row: 1 / span 1;
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
        }
        div.devtools {
            width: 345px;
            height: auto;
            text-align: left;
            grid-column: 2 / span 1;
            grid-row: 2 / span 1;
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
                margin-top: 78px;
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
        @media screen and (max-width: 450px) {
            width: 280px;
            display: block;
            height: auto;
            img.phone {
                width: 280px;
                height: auto;
            }
            div.description {
                width: 280px;
                margin: 40px auto;
                h4, p {
                    text-align: center;
                }
            }
            div.devtools {
                width: 280px;
                margin: 40px auto;
                h6 {
                    text-align: center;
                }
                div.tech_grid {
                    width: 280px;
                    margin: 20px auto;
                    div.icon {
                        img {
                            left: 50%;
                            transform: translateY(-50%) translateX(-50%);
                        }
                    }
                }
            }
        }
    }
}

</style>
