<template>
  <div v-if="show" class="dialog">
    <div class="dialog__content">
      <form @submit.prevent="submitForm" class="dialog__form">
        <input v-model="formData.name" type="text" placeholder="Имя" class="dialog__input" />
        <input v-model="formData.email" type="email" placeholder="Email" class="dialog__input" />
        <div class="dialog__buttons">
          <button type="submit" class="dialog__button dialog__button--submit">Отправить</button>
          <button @click="closeDialog" class="dialog__button dialog__button--close">Закрыть</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineProps({
  show: {
    type: Boolean,
    required: true
  }
})

const emit = defineEmits(['close', 'submit'])
const formData = ref({
  name: '',
  email: ''
})

const closeDialog = () => {
  emit('close')
}

const submitForm = () => {
  emit('submit', formData.value)
  closeDialog()
}
</script>

<style scoped>
.dialog {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}

.dialog__content {
  background: #fff;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
}

.dialog__form {
  display: flex;
  flex-direction: column;
}

.dialog__input {
  margin-bottom: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.dialog__buttons {
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
}

.dialog__button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  color: #fff;
  cursor: pointer;
}

.dialog__button--submit {
  background-color: #007bff;
}

.dialog__button--submit:hover {
  background-color: #0056b3;
}

.dialog__button--close {
  background-color: #dc3545;
}

.dialog__button--close:hover {
  background-color: #c82333;
}
</style>
