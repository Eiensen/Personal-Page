<template>
<div class="block block--lesson">
<div class="block-component">
    <span class="block-component__title">{{ title }}</span>
    <div class="block-component__container">
        <div class="block-component__container__card">

        </div>
        <div class="block-component__container__card">
            
        </div>
        <div class="block-component__container__card">
            
        </div>
    </div>
    <button class="block-component__button" @click="handleClick">Записаться на занятие</button>
</div>
</div>
</template>

<script setup lang="ts">

const title: string = "Форматы занятий";
const emit = defineEmits(['click']);

const handleClick = () => {
    emit('click')
}
</script>

<style scoped>
.block--lesson{
    background-image: url("../../assets/bg/bg-lessonFormats-1.webp");
    background-position: center;
    background-size: cover;
    padding-top: 3%;
}
.block.block--lesson{
    height: 90vh;
}

.block-component__container{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
}

.block-component__container__card{
    background-color: rgba(0, 0, 0, 0.6);
    height: 50vh;
    width: 20%;
    border-radius: 25px;
    margin: 5%;
}
</style>