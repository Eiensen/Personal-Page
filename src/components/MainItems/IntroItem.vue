<template>
  <div class="block block--title">
    <div class="block-component">
      <span class="block-component__title">{{ title }}</span>
      <span class="block-component__subtitle">{{ subtitle }}</span>
      <p class="block-component__description" v-html="description"></p>
      <button class="block-component__button" @click="handleClick">Записаться на занятие</button>
    </div>
  </div>
</template>

<script setup lang="ts">
const title: string = 'АНГЛИЙСКИЙ'
const subtitle: string = 'для твоих целей'
const description: string =
  'Занятия, на которых ты научишься свободно <span style="color: #d0a933;">говорить</span> и <span style="color: #d0a933;">понимать</span> носителей'

const emit = defineEmits(['click'])

const handleClick = () => {
  emit('click')
}
</script>

<style scoped>
.block.block--title {
  background-image: url('../../assets/bg/bg-title.JPG');
  background-size: cover;
  background-position: center;
  padding: 8% 13%;
}
.block--title > .block-component{
  width: min-content;
}

@media screen and (min-width: 1600px) {
  .block--title {
    padding: 5% 20%;
  }
}

</style>
