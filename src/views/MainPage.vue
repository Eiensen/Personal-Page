<template>
  <div class="main-content">
    <IntroItem @click="handleBlockClick" />
    <LessonFormatsItem />
    <DialogForm :show="showDialog" @close="showDialog = false" @submit="handleFormSubmit">
      <!-- Содержимое диалогового окна -->
      <p>Привет, это диалоговое окно!</p>
    </DialogForm>
  </div>
</template>

<script setup lang="ts">
import DialogForm from '@/components/MainItems/DialogForm.vue'
import IntroItem from '../components/MainItems/IntroItem.vue'
import { ref } from 'vue'
import LessonFormatsItem from '@/components/MainItems/LessonFormatsItem.vue';

const showDialog = ref(false)

const handleFormSubmit = (formData: any) => {
  console.log('Форма отправлена:', formData)
  // Здесь можно выполнить дополнительную логику после отправки формы
}

const handleBlockClick = () => {
  showDialog.value = true
  console.log('handle Block Clicked')
}
</script>

<style scoped>
.main-content {
  width: 100%;
  background-color: rgb(64, 57, 39);
}
</style>

<style>
.block {
  width: 100%;
  height: 80vh;
  background-color: #352f1f;
}

.block-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
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

@media screen and (min-width: 701px) and (max-width: 940px) {
  .block-component__title {
    font-size: 60px;
  }
  .block-component__subtitle {
    font-size: 37px;
  }
  .block-component__description {
    font-size: 25px;
  }
  .block-component__button {
    font-size: 16px;
    width: 80%;
    margin-top: 200px;
  }
}

@media screen and (min-width: 500px) and (max-width: 720px) {
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
    font-size: 20px;
    margin-left: -80px;
  }
  .block-component__button {
    font-size: 16px;
    width: 80%;
    margin-top: 300px;
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
    margin-top: 350px;
  }
}
</style>
