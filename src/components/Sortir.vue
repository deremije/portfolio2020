<template>
    <section class='sortir' id='sortir'>
        <div class='center_box'>
            <div class='description'>
                <h4>
                    <a href="https://www.sortir.io" target="_blank" rel="noreferrer">Sortir.io</a>
                </h4>
                <p>
                    Confinement project: Making the "Attestation de déplacement dérogatoire" easier and faster to create during lockdown.
                </p>
                <p>
                    I took a privacy-centered approach, utilizing browser local storage and an open-source PDF editing library to bring documentation generation down to a single tap without jeopardizing a user's sensitive personal information.
                </p>
                <p>
                    Developed in React.js, and built out as a Progressive Web App
                </p>
            </div>
            <img class='phone howto' src='images/sortir-howto.jpg' alt="How To view in Sortir.io" />
            <img class='phone reason' src='images/sortir-reason.jpg' alt="Quick Reason Select in Sortir.io" />
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
section.sortir {
    background-color: #eeeeee;
    display: flex;
    div.center_box {
        margin: auto;
        width: calc(100% - 200px);
        max-width: 1000px;
        height: auto;
        display: grid;
        grid-template-columns: 268px 268px 1fr;
        grid-column-gap: 47px;
        img.phone {
            display: block;
            width: 100%;
            height: auto;
            border: solid 3px black;
        }
        img.howto {
            grid-column: 1;
            grid-row: 1;
        }
        img.reason {
            grid-column: 2;
            grid-row: 1;
        }
        div.description {
            width: 100%;
            height: auto;
            text-align: left;
            margin-top: 60px;
            grid-column: 3;
            grid-row: 1;
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
                padding: 10px 0;
                text-align: left;
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
