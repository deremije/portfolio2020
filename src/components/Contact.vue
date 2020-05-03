<template>
    <section>
        <div class='contact_card'>
            <div class='details'>
                <h3>Jeremy Randall</h3>
                <h4>jeremy@deremije.com</h4>
                <div class='phones'>
                    <h5><img class='flag' src='images/usa.png' />+1 (812) 827-4414</h5>
                    <h5><img class='flag' src='images/france.png' />+33 (0)6 22 51 22 82</h5>
                </div>
            </div>
            <img class='profile_pic' src='images/jeremy.png' />
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
.contact_card {
    width: 1000px;
    height: 400px;
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    div.details {
        height: auto;
        width: 400px;
        position: absolute;
        bottom: 60px;
        left: 0;
        display: flex;
        flex-direction: column;
        div.phones {
            margin: 20px 0 0 0;
        }
        img.flag {
            height: 22px;
            width: auto;
            position: relative;
            top: 4px;
            margin-right: 10px;
        }
        h3 {
            margin: 0;
            padding: 12px 0;
            font-family: Comfortaa, sans-serif;
            text-align: left;
            font-size: 36px;
            line-height: 36px;            
        }
        h4 {
            margin: 0;
            padding: 0;
            font-family: Comfortaa, sans-serif;
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
        width: 400px;
        height: 400px;
        border-radius: 5px;
        position: absolute;
        right: 0;
    }
}
</style>
