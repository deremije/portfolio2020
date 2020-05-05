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
        height: auto;
        display: grid;
        grid-template-columns: 268px 1fr;
        grid-template-rows: 216px 1fr;
        grid-column-gap: 47px;
        img.phone {
            display: block;
            width: 100%;
            height: auto;
            grid-column: 1 / span 1;
            grid-row: 1 / span 2;
        }
        div.description {
            width: 100%;
            height: auto;
            text-align: left;
            grid-column: 2 / span 1;
            grid-row: 1 / span 1;
            margin-top: 60px;
            h4 {
                font-family: Comfortaa, sans-serif;
                font-weight: 400;
                font-size: 36px;
                line-height: 52px;
                margin: 0px 0 5px 0;
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
            width: 100%;
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
                height: auto;
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
        @media screen and (max-width: 740px) {
            width: 480px;
            grid-template-columns: 200px 1fr;
            grid-template-rows: 160px 1fr;
            grid-column-gap: 27px;
            div.description {
                margin: 0px auto;
            }
            div.devtools {
                div.tech_grid {
                    margin: 20px auto;
                }
            }
        }
        @media screen and (max-width: 520px) {
            width: 280px;
            display: block;
            height: auto;
            img.phone {
                margin: 20px 0;
            }
            div.description {
                h4, p {
                    text-align: center;
                }
            }
            div.devtools {
                h6 {
                    text-align: center;
                }
                div.tech_grid {
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
