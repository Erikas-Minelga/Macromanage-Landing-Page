<script setup>
    import Btn from './Btn.vue';
</script>

<template>
    <div id="hero" class="flex-column">
        <div class="flex-row">
            <div>
                <h1 class="white-txt">Elevate your team's productivity with Macromanage</h1>
                <p class="white-txt">Join our industry-leading platform for all your task tracking needs!</p>
                <form>
                    <input type="email" placeholder="Enter your email">
                    <Btn colour="orange" id="0">Get Started</Btn>
                </form>
            </div>
            <img src="/img/hero_image.png">
        </div>
    </div>
</template>

<style scoped>
    #hero{
        height: fit-content;
    }

    #hero > div:first-child
    {
        background-image: linear-gradient(180deg, #240D82 0%, #4B379B 68%, #A29AC2 99%);
        height: 488px;
        width: 100%;
        column-gap: 5vw;
        flex-wrap: wrap;
    }

    #hero > div:first-child > div
    {
        margin-top: 50px;
    }

    p, form
    {
        margin-top: 30px;
    }

    h1{
        width: 392px;
    }

    img{
        height: clamp(300px,20vw,400px);
        width: clamp(300px,20%,400px);
        position: relative;
        top: 120px;
    }

    input{
        width: 375px;
        height: 42px;
        border-radius: 10px;
        color: #595959;
        margin-right: 10px;
        padding-left: 10px;
    }

    @media screen and (max-width: 854px){

        #hero{
            text-align: center;
            height: fit-content;
        }

        h1, p{
            width: 100vw;
        }

        #hero > *{
            margin-right: auto;
            margin-left: auto;
        }

        #hero > div:first-child{
            height: fit-content;
        }

        form{
            display: flex;
            flex-direction: column;
        }

        input{
            margin: 0;
            margin-left: auto;
            margin-right: auto;
            width: 95vw;
        }

        button{
            margin-top: 8px;
            margin-right: auto;
            margin-left: auto;
        }

        img{
            position: static;
        }
    }
</style>