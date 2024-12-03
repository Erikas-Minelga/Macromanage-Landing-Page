<script setup>
    import Btn from './Btn.vue';
</script>

<template>
    <div class="white-txt">
        <h2 class="text-center">Sign up and start Macromanaging your team today!</h2>
        <p class="text-center">And also get 30 days of full access on us! Cancel anytime.</p>
        <div class="flex-row">
            <Btn colour="orange" id="0">Start your free trial</Btn>
        </div>
    </div>
</template>

<style scoped>
    div:not([class="flex-row"]){
        height: fit-content;
        background-color: #322568;
        padding: 30px 0 30px 0;
    }

    button{
        margin-right: auto;
        margin-left: auto;
        width: 190px;
    }

    p,button{
        margin-top: 16px;
    }
</style>