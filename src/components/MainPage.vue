<template>
  <div class="main-content">
    <BlockItem
      title="АНГЛИЙСКИЙ"
      subtitle="для твоих целей"
      :description="styledDescriptionForTitle"
      button-text="Записаться на занятие"
      backgroundImage="title"
      @click="handleBlockClick"
    />
    <BlockItem
      title="Title 2"
      description="Description for block 2."
      button-text="Button 2"
      @click="handleBlockClick"
    />
    <BlockItem
      title="Title 3"
      description="Description for block 3."
      button-text="Button 3"
      @click="handleBlockClick"
    />
    <BlockItem
      title="Title 4"
      description="Description for block 4."
      button-text="Button 4"
      @click="handleBlockClick"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import BlockItem from './BlockItem.vue'

export default defineComponent({
  components: {
    BlockItem
  },
  setup() {
    const handleBlockClick = () => {
      console.log('handleBlockClick')
    }
    const styledDescriptionForTitle: string =
      'Занятия, на которых ты научишься свободно <span style="color: #d0a933;">говорить</span> и <span style="color: #d0a933;">понимать</span> носителей'
    return {
      handleBlockClick,
      styledDescriptionForTitle
    }
  }
})
</script>

<style scoped>
.main-content {
  width: 100%;
  background-color: rgb(64, 57, 39);
}
</style>
