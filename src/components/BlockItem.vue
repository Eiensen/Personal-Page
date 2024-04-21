<template>
  <div :class="`block-component block-component--${backgroundImage}`">
    <span class="block-component__title">{{ title }}</span>
    <span class="block-component__subtitle">{{ subtitle }}</span>
    <p class="block-component__description" v-html="description"></p>
    <button class="block-component__button" @click="handleClick">{{ buttonText }}</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {
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
  },
  emits: ['click'],
  methods: {
    handleClick() {
      this.$emit('click')
    }
  }
})
</script>

<style scoped>
.block-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 5% 15%;
  width: 100%;
  min-height: 80vh;
}

.block-component--title {
  background-image: url('../assets/bg/bg-title.JPG');
  background-size: cover;
  background-position: center;
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
</style>
