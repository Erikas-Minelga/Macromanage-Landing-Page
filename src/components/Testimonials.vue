<script setup>
    import testimonials from './data/testimonials.js';
    import { ref } from 'vue';
    import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
    import { faCaretRight, faCaretLeft } from '@fortawesome/free-solid-svg-icons';
    
    const count = ref(0);
    const fade = ref(false);

    let interval = setInterval(countUp, 5000);

    function resetInterval()
    {
        clearInterval(interval);
        interval = setInterval(countUp, 5000);
    }

    function countUp()
    {
        if(count.value === 3)
            count.value = 0;
        else
            count.value++;

        fade.value = true;

        resetInterval();
    }

    function countDown()
    {
        if(count.value === 0)
            count.value = 3;
        else
            count.value--;

        fade.value = true;

        resetInterval();
    }

    function resetFade()
    {
        fade.value = false;
    }

</script>

<template>
    <section>
        <h1 class="text-center">Don't just take our word for it. Listen to what our customers have to say!</h1>
        <div>
            <div id="controls" class="flex-row">
                <FontAwesomeIcon :icon="faCaretLeft" @click="countDown"></FontAwesomeIcon>
                <p class="text-center"><span>{{ count+1 }}</span>/4</p>
                <FontAwesomeIcon :icon="faCaretRight" @click="countUp"></FontAwesomeIcon>
            </div>
            <div class="flex-row">
                <div>
                    <div id="speech-bubble" class="flex-column">
                        <p class="text-center" :class="fade === true ? 'fade' : ''" @animationend="resetFade">{{ testimonials.data[count].text }}</p>
                    </div>
                    <div class="flex-row">
                        <div class="flex-column">
                            <img :src="testimonials.data[count].image_src" :class="fade === true ? 'fade' : ''" @animationend="resetFade">
                            <div>
                                <p class="text-center">{{ testimonials.data[count].name }}</p>
                                <p class="text-center">{{ testimonials.data[count].job_title }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
    section{
        height: 559px;
        background-image: linear-gradient(180deg, #f2f3f5 62%, #FFFFFF 100%);
        margin-bottom: 100px;
    }

    section > div{
        margin-top: 30px;
    }

    #controls{
        column-gap: 4vw;
        margin-bottom: 12px;
    }

    #controls > p{
        align-self: center;
    }

    button{
        height: 30px;
        width: 60px;
    }

    #speech-bubble{
        position: relative;
        background-color: #FFFFFF;
        height: 253px;
        width: clamp(200px,40vw,503px);
        border-radius: 63px;
        padding: 15px;
        justify-content: center;
    }

    #speech-bubble::after{
        content: '';
        position: absolute;
        bottom: 0;
        left: 50%;
        width: 0;
        height: 0;
        border: 20px solid transparent;
        border-top-color: #FFFFFF;
        border-bottom: 0;
        margin-left: -20px;
        margin-bottom: -20px;
    }

    #speech-bubble > p{
        line-height: 25px;
    }

    img{
        height: 130px;
        width: 130px;
        border-radius: 100%;
        position: relative;
        margin-top: 25px;
        left: 50px;
        background-size: contain;
    }

    img + div{
        width: 230px;
    }

    /* Font Awesome icons */
    svg{
        height: 50px;
        width: 50px;
        color: #878686;
    }

    svg:hover{
        cursor: pointer;
    }

    @media screen and (max-width: 768px) {
        #speech-bubble{
            width: 70vw;
        }
    }
</style>