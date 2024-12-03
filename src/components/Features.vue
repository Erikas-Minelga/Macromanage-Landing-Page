<script setup>
    import Btn from './Btn.vue';
    import { ref } from 'vue';
    import features from './data/features.js';

    const selectedId = ref('0');
    const fade = ref(false);


    function switchFeature(newId)
    {
        selectedId.value = newId;
        fade.value = true;
    }

    function removeClass()
    {
        fade.value = false;
    }

</script>

<template>
    <section>
            <h1 class="text-center">Packed with so many features, Macromanage is an obvious choice if you are looking for:</h1>
            <div class="flex-row">
                <div id="features-container" class="flex-column">
                    <div id="toggles" class="flex-row">
                        <Btn :colour="selectedId === '0' ? 'blue' : 'white'" id="0" @clicked="(id) => switchFeature(id)">KANBAN Boards</Btn>
                        <Btn :colour="selectedId === '1' ? 'blue' : 'white'" id="1" @clicked="(id) => switchFeature(id)">Workflow Automation</Btn>
                        <Btn :colour="selectedId === '2' ? 'blue' : 'white'" id="2" @clicked="(id) => switchFeature(id)">Statistics Tracking</Btn>
                    </div>
                    <div id="description-container" class="flex-row" :class="fade === true ? 'fade': ''" @animationend="removeClass">
                        <div>
                            <h2 class="text-center">{{ features.data[selectedId].header }}</h2>
                            <ul>
                                <li v-for="item in features.data[selectedId].list_items">
                                    <span>{{ item.first_word }}</span>
                                    {{ item.remaining_text }}
                                </li>
                            </ul>
                        </div>
                        <img :src="features.data[selectedId].image">
                    </div>
                </div>
            </div>
    </section>
</template>

<style scoped>
    section{
        height: fit-content;
        background-color: #f2f3f5;
        justify-content: space-around;
        padding: 35px;
    }

    #features-container{
        border-radius: 15px;
        background-color: #ffffff;
        padding: 30px;
        width: 65vw;
        justify-content: space-evenly;
        margin-top: 15px;
    }

    #toggles{
        column-gap: 1vw;
        margin-bottom: 30px;
        margin-top: -15px;
        flex-wrap: wrap;
    }

    #description-container{
        flex-wrap: wrap;
        column-gap: 1vw;
    }

    h2{
        margin-bottom: 25px;
    }

    ul{
        width: 25vw;
    }

    span{
        font-weight: bold;
    }

    img{
        height: 305px;
        width: 388px;
    }

    @media screen and (min-width: 929px) and (max-width: 1610px){
        #features-container{
            width: 85vw;
        }
    }

    @media screen and (max-width: 928px)
    {
        #features-container{
            width: 90vw;
        }

        img{
            margin-top: 20px;
            width: 70vw;
            max-width: 388px;
            height: 60vw;
            max-height: 305px;
        }

        ul{
            width: 70vw;
        }
    }
</style>