<template>
    <footer>
        <div>
            Copyright 2020 Jeremy Randall
        </div>
        <div class='social_icons'>
            <a href='https://www.linkedin.com/in/jeremy-randall-61217919/' target='_blank'>
                <img src='images/linkedin.png' alt="LinkedIn" />
            </a>
            <a href='https://www.github.com/deremije' target='_blank'>
                <img src='images/github.png' alt="Github" />
            </a>
            <a href='https://www.codepen.io/deremije' target='_blank'>
                <img src='images/codepen.png' alt="CodePen" />
            </a>
            <a href='https://www.freecodecamp.org/%C4%91eremije' target='_blank'>
                <img src='images/fcc.png' alt="FreeCodeCamp" />
            </a>
        </div>
        <div>
            <a href='resume.pdf' target='_blank'>Download my resume PDF</a>
        </div>
        
    </footer>
</template>

<style lang="scss" scoped>

    footer {
        font-family: Raleway, sans-serif;
        font-size: 18px;
        height: 60px;
        line-height: 60px;
        padding: 10px 40px;
        width: auto;
        background-color: #e1e1e1;
        transition: all 200ms linear;
        text-align: left;
        display: flex;
        justify-content: space-evenly;
        position: relative;
        div {
            width: 350px;
            text-align: center;
        }
        div.social_icons {
            display: flex;
            justify-content: center;
            img {
                height: 40px;
                width: auto;
                margin: 10px;
            }
        }
        @media screen and (max-width: 1049px) {
            div {
                width: 280px;
                font-size: 14px;
            }
        }
        @media screen and (max-width: 750px) {
            height: auto;
            padding: 20px calc(50% - 140px);
            margin: auto;
            width: 280px;
            text-align: center;
            flex-direction: column;
            div {
                width: 280px;
                height: 60px;
                font-size: 18px;
            }
        }
    }
</style>