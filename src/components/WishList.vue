<template>
  <h1>Wish List</h1>
  <app-card
    v-for="(item, index) in cards"
    :key="item.id"
    :card="item"
    :index="index"
    @click="($event) => emit('click-by-card', item)" />
</template>

<script setup>
import AppCard from "./AppCard.vue"

const props = defineProps({
  cards: {
    type: Array,
  },
})

const emit = defineEmits(["click-by-card"])
</script>

<style scoped>
@import "../assets/global.css";

.card {
  width: 300px;
  padding: 24px 24px 16px;
  background-color: #f0ebeb;
  border-radius: 16px;
  margin-bottom: 16px;
}

.card-title {
  font-size: 18px;
  font-weight: 600;
  margin-bottom: 8px;
}

.card-description {
  color: rgb(106, 109, 114);
  margin-bottom: 16px;
}

.card-completed {
  display: flex;
  align-items: center;
  gap: 4px;
}

.card-is-completed {
  padding: 0 6px;
  border: 1px solid rgb(42, 182, 231);
  color: rgb(42, 182, 231);
  border-radius: 4px;
}

.card-is-not-completed {
  padding: 0 6px;
  border: 1px solid rgb(166, 182, 197);
  color: rgb(166, 182, 197);
  border-radius: 4px;
}

.form {
  margin-bottom: 12px;
}

input {
  margin-left: 4px;
  margin-bottom: 8px;
}
</style>
