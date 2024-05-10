<template>
  <div class="main-content">
    <IntroItem @click="handleBlockClick" />
    <DialogForm :show="showDialog" @close="showDialog = false" @submit="handleFormSubmit">
      <!-- Содержимое диалогового окна -->
      <p>Привет, это диалоговое окно!</p>
    </DialogForm>
  </div>
</template>

<script setup lang="ts">
import DialogForm from '@/components/DialogForm.vue'
import IntroItem from '../components/IntroItem.vue'
import { ref } from 'vue'

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
