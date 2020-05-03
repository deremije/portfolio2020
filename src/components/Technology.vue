<template>
    <section class='technology'>
        <p>
            My level of expertise varies between these technologies,
            but I've used each of them to complete personal and professional 
            projects. 
        </p>
        <div class='tech_grid'>
            <div class='image_wrapper' v-for='icon in tech' :key='icon'>
                <img :class='icon' :src='"images/" + icon + ".png"' :alt='icon' />
            </div>
        </div>
        <p>
            Can we please start calling my favorite stack VENoM?<br />
            (Vue.js, Express.js, Node.js, MongoDB)
        </p>
    </section>
</template>

<script>
export default {
    name: 'Technology',
    data() {
        return {
            tech: [
                'html_js_css',
                'figma',
                'gimp',
                'vuejs',
                'react',
                'git',
                'nodejs',
                'express',
                'mongodb',
                'cordova',
                'python',
                'flask',
            ]
        }
    },
}
</script>

<style scoped lang="scss">
section.technology {
    background-color: #EEEEEE;
    p {
        font-family: Comfortaa, sans-serif;
        font-size: 18px;
        line-height: 27px;
        text-align: center;
        margin: 50px auto;
        width: 630px;
    }
    div.tech_grid {
        width: 900px;
        height: 480px;
        display: grid;
        margin: auto;
        grid-template-columns: repeat(3, 300px);
        grid-template-rows: repeat(4, 120px);
        div.image_wrapper {
            display: flex;
            img {
                display: block;
                margin: auto;
                max-height: 70px;
                max-width: 130px;
            }
        }
    }
}
</style>
