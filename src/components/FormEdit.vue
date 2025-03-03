<template>
  <h2>Форма редактирования</h2>
  <form @submit.prevent="saveCard" class="form">
    <label>
      <span>Название:</span>
      <input type="text" :value="card.title" @input="setTitle" />
    </label>
    <label>
      <span>Описание:</span>
      <input type="text" :value="card.description" @input="setDescription" />
    </label>
    <button type="submit">Сохранить</button>
  </form>
</template>

<script setup>
const props = defineProps({
  card: {
    type: Object,
  },
})

const emit = defineEmits(["set-card", "save-card"])

const setTitle = (event) => {
  const data = Object.assign({}, props.card)
  data.title = event.target.value
  emit("set-card", data)
}
const setDescription = (event) => {
  const data = Object.assign({}, props.card)
  data.description = event.target.value
  emit("set-card", data)
}

const saveCard = () => {
  emit("save-card")
}

// const addCard = () => {
//   emit("set-card", newCard.value)
//   console.log(newCard.value)
// }
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
