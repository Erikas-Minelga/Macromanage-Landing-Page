<script setup>
    const props = defineProps(['colour', 'id']);
</script>

<template>
    <button :class="props.colour" @click="$emit('clicked', props.id)">
        <slot>CTA Goes Here</slot>
    </button>
</template>

<style scoped>

    button{
        width: fit-content;
        height: 31px;
        padding: 5px;
        border-radius: 15px;
    }

    button:hover{
        cursor: pointer;
    }

    .white{
        background-color: #FFFFFF;
        border: 1px solid #5100FF;
    }

    .blue, white:hover{
        background-color: rgba(81,0,255,0.76);
        color: white;
    }

    .blue:hover{
        background-color: rgb(50, 0, 159);
    }

    .orange{
        background-color: #FF4800;
        color: white;
    }

    .orange:hover{
        background-color: #c73800;
    }

    @media screen and(max-width: 768px) {
        button{
            height: fit-content;
        }
    }

</style>