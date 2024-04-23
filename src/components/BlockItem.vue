<template>
  <div :class="`block block--${backgroundImage}`">
    <div class="block-component">
      <span class="block-component__title">{{ title }}</span>
      <span class="block-component__subtitle">{{ subtitle }}</span>
      <p class="block-component__description" v-html="description"></p>
      <button class="block-component__button" @click="handleClick">{{ buttonText }}</button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  title: {
    type: String,
    required: true
  },
  subtitle: {
    type: String,
    required: false
  },
  description: {
    type: String,
    required: true
  },
  buttonText: {
    type: String,
    required: true
  },
  backgroundImage: {
    type: String,
    default: ''
  }
})
const emit = defineEmits(['click'])

const handleClick = () => {
  emit('click')
}
</script>

<style scoped>
.block {
  width: 100%;
  height: 80vh;
}
.block-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: min-content;
}

.block--title {
  background-image: url('../assets/bg/bg-title.JPG');
  background-size: cover;
  background-position: center;
  padding: 8% 13%;
}
.block-component__title {
  margin: 0;
  padding: 0;
  font-size: 76px;
  color: #fff;
}
.block-component__subtitle {
  margin: 0;
  padding: 0;
  font-size: 52px;
  color: #d0a933;
}

.block-component__description {
  font-size: 22px;
  color: #fff;
  width: 65%;
  margin-top: 50px;
  text-align: center;
}

.block-component__button {
  padding: 10px 20px;
  justify-self: center;
  background-color: #d0a933;
  color: #fff;
  font-size: 18px;
  border: none;
  cursor: pointer;
  border-radius: 25px;
  width: 50%;
  margin-top: 50px;
}

@media screen and (min-width: 1600px) {
  .block--title {
    padding: 5% 20%;
  }
}

@media screen and (min-width: 500px) and (max-width: 1000px) {
  .block {
    display: flex;
    justify-content: center;
  }
  .block-component__title {
    font-size: 50px;
  }
  .block-component__subtitle {
    font-size: 32px;
  }
  .block-component__description {
    font-size: 18px;
    margin-left: -80px;
  }
  .block-component__button {
    font-size: 16px;
    width: 80%;
    margin-top: 200px;
  }
}

@media screen and (max-width: 499px) {
  .block {
    display: flex;
    justify-content: center;
  }
  .block-component__title {
    font-size: 40px;
  }
  .block-component__subtitle {
    font-size: 24px;
  }
  .block-component__description {
    font-size: 16px;
  }
  .block-component__button {
    font-size: 14px;
    width: 80%;
    margin-top: 250px;
  }
}
</style>
