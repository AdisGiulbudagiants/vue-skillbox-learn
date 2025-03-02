<template>
  <div class="container">
    <FormCreate />
    <WishList :cards="cards" />
  </div>
</template>

<script setup>
import { ref } from "vue"
import WishList from "./components/WishList.vue"
import FormCreate from "./components/FormCreate.vue"

const cards = ref([
  {
    id: 1,
    title: "Ноутбук",
    description: "Я хочу получить в подарок новый ноутбук",
    completed: false,
  },
  {
    id: 2,
    title: "Наушники",
    description: "Я хочу получить в подарок наушники для ноутбука",
    completed: true,
  },
  {
    id: 3,
    title: "Мышка",
    description: "Я хочу получить в подарок мышку для ноутбука",
    completed: false,
  },
])
</script>

<style scoped>
@import "./assets/global.css";
</style>
