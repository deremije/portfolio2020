<template>
    <section class='contact' id='contact'>
        <div class='contact_card'>
            <div class='details'>
                <h3>Jeremy Randall</h3>
                <h4><a href='mailto:jeremy@deremije.com'>jeremy@deremije.com</a></h4>
                <div class='phones'>
                    <h5><a href='tel:8128274414'><img class='flag' src='images/usa.png' />+1 (812) 827-4414</a></h5>
                    <h5><a href='tel:622512282'><img class='flag' src='images/france.png' />+33 (0)6 22 51 22 82</a></h5>
                </div>
            </div>
            <img class='profile_pic' src='images/logo.svg' />
        </div>
    </section>
</template>

<script>
export default {
    name: 'Contact',
    data() {
        return {
        }
    },
    methods: {
    }
}
</script>

<style scoped lang="scss">
section.contact {
    display: flex;
    background-color: #F3F3F3;
}
div.contact_card {
    width: 950px;
    height: 400px;
    position: relative;
    margin: auto;
    div.details {
        height: auto;
        width: 400px;
        position: absolute;
        bottom: 50%;
        left: 0;
        transform: translateY(50%);
        display: flex;
        flex-direction: column;
        a {
            text-decoration: none;
            color: #2c3e50;
        }
        div.phones {
            margin: 20px 0 0 0;
            img.flag {
                height: 22px;
                width: auto;
                position: relative;
                top: 4px;
                margin-right: 10px;
            }
        }
        h3 {
            margin: 0;
            padding: 12px 0;
            font-family: Raleway, sans-serif;
            font-weight: 300;
            text-align: left;
            font-size: 36px;
            line-height: 36px;            
        }
        h4 {
            margin: 0;
            padding: 0;
            font-family: Raleway, sans-serif;
            font-weight: 400;
            text-align: left;
            font-size: 22px;
        }
        h5 {
            margin: 0;
            padding: 6px 0;
            font-family: Comfortaa, sans-serif;
            text-align: left;
            font-size: 16px;
            line-height: 22px;
            height: 22px;
        }
    }
    img.profile_pic {
        display: block;
        width: 600px;
        height: auto;
        border-radius: 5px;
        position: absolute;
        right: 0;
        bottom: 50%;
        transform: translateY(50%);
    }
    @media screen and (max-width: 450px) {
        width: 280px;
        height: auto;
        display: flex;
        flex-direction: column-reverse;
        div.details,
        img.profile_pic {
            width: 100%;
            position: relative;
            bottom: auto;
            transform: translateY(0);
            padding: 20px 0;
        }
    }
}
</style>
