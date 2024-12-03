<script setup>
    import { useIntersectionObserver } from '@vueuse/core';
    import { ref } from 'vue';

    const metrics = ref(null);
    const elementVisible = ref(false);

    const {stop} = useIntersectionObserver(
        metrics,
        ([entry], observerElement) => {
            elementVisible.value = entry?.isIntersecting || false
        },
    )

</script>

<template>
    <section class="flex-column">
        <h1 class="text-center">Let the numbers speak for themselves</h1>
        <div class="flex-row metrics" ref="metrics">
            <div class="flex-column" :class="elementVisible === true ? 'visible' : ''">
                <p class="text-center">Productivity Increase</p>
                <div id="metric-1" class="round flex-column text-center bold-txt">90%</div>
                <p class="text-center">on average</p>
            </div>
            <div class="flex-column" :class="elementVisible === true ? 'visible' : ''">
                <p class="text-center">Workflow Improved By</p>
                <div id="metric-2" class="round flex-column text-center bold-txt">90%</div>
                <p class="text-center">on average</p>
            </div>
            <div class="flex-column" :class="elementVisible === true ? 'visible' : ''">
                <p class="text-center">User Satisfaction</p>
                <div id="metric-3" class="round flex-column text-center bold-txt">100%</div>
                <p class="text-center">of all users</p>
            </div>
        </div>
    </section>
</template>

<style scoped>
    @keyframes slide-from-left {
        0%{right: 100px; opacity: 0;}
        100% {right: 0; opacity: 1;}
    }

    @keyframes slide-from-right {
        0%{left: 100px; opacity: 0;}
        100% {left: 0; opacity: 1;}
    }

    @keyframes slide-from-bottom {
        0%{top: 100px; opacity: 0;}
        100% {top: 0; opacity: 1;}
    }

    section{
        height: fit-content;
        justify-content: space-around;
    }

    .metrics{
        flex-wrap: wrap;
        column-gap: 15vw;
    }

    .visible{
        position: relative;
    }

    .visible:nth-child(1){
        animation: slide-from-left 0.8s ease-in;
    }

    .visible:nth-child(2){
        animation: slide-from-bottom 0.8s ease-in;
    }

    .visible:nth-child(3){
        animation: slide-from-right 0.8s ease-in;
    }

    .flex-column{
        row-gap: 10px;
    }

    @media screen and (max-width: 768px) {
        div > div{
            column-gap: 0;
        }
    }

    @media screen and (max-width: 571px)
    {
        .visible:nth-child(1){
            animation: slide-from-left 0.8s ease-in;
        }

        .visible:nth-child(2){
            animation: slide-from-right 0.8s ease-in;
        }

        .visible:nth-child(3){
            animation: slide-from-bottom 0.8s ease-in;
        }
    }

    div > p:first-child{
        width: 105px;
        font-weight: bold;
    }

    img{
        height: 110px;
        width: 110px;
    }

    .round{
        height: 110px;
        width: 110px;
        border-radius: 100%;
        background-color: #E0EBFF;
        justify-content: center;
        font-size: xx-large;
    }
</style>