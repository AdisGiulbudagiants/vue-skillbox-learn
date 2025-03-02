<template>
  <h2>Форма создания</h2>
  <form @submit.prevent="addCard" class="form">
    <label>
      <span>Название:</span>
      <input type="text" v-model="newCard.title" />
    </label>
    <label>
      <span>Описание:</span>
      <input type="text" v-model="newCard.description" />
    </label>
    <button type="submit">Добавить</button>
  </form>
</template>

<script setup>
import { ref } from "vue"

const newCard = ref({
  id: 0,
  title: "",
  description: "",
  completed: false,
})

const addCard = () => {
  console.log(newCard.value)
}
</script>

<style scoped>
.form {
  display: flex;
  flex-direction: column;
  margin-bottom: 12px;
}

input {
  margin-left: 4px;
  margin-bottom: 8px;
}

button {
  width: 180px;
}
</style>
