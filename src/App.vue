<template>
    <div id="app">
        <Header :show='show'></Header>
        <Hero></Hero>
        <AboutMe></AboutMe>
        <Technology></Technology>
        <WorkSamples @add_scoop='add_scoop'></WorkSamples>
        <Kiddooo></Kiddooo>
        <Contact></Contact>
        <Footer></Footer>
        <IceCream :scoops='scoops'></IceCream>
    </div>
</template>

<script>
import Header from './components/Header.vue';
import AboutMe from './components/AboutMe.vue';
import Technology from './components/Technology.vue';
import WorkSamples from './components/WorkSamples.vue';
import Contact from './components/Contact.vue';
import Hero from './components/Hero.vue';
import Kiddooo from './components/Kiddooo.vue';
import Footer from './components/Footer.vue';
import IceCream from './components/IceCream.vue';

export default {
    name: 'App',
    components: {
        WorkSamples, Header, AboutMe, Technology, Contact, Hero, Kiddooo, Footer, IceCream
    },
    data() {
        return {
            show_blank: true,
            show: {
                logo: true,
            },
            scoops: []
        }
    },
    computed: {
        open() {
            return this.show_menu ? 'open' : '';
        },
    },
    methods: {
        display_view(view) {
            this.active_view = view;
        },
        add_scoop(flavor) {
            this.scoops.push(flavor);
        }
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@500&family=Didact+Gothic&family=Raleway:wght@400;600&display=swap');

html {
    scroll-behavior: smooth;
}
html, body {
    margin: 0;
    padding: 0;
    width: 100vw;
    
}

#app {
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    width: 100%;
    height: 100vh;
    overflow: auto;
    
    p {
        font-family: 'Didact Gothic', sans-serif;
        font-size: 18px;
    }
    a {
        text-decoration: none;
    }
    section {
        width: 100%;
            padding: 40px 0;
            height: auto;
        overflow: hidden;
        @media screen and (max-width: 1024px) {
        }
    }
    
    @keyframes fade_into_view {
        from { opacity: 0 }
        to { opacity: 1 }
    }
}
</style>
