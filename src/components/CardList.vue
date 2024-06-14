<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      :image-url="'/sneakers/sneakers-1.jpg'"
      :title="'Кроссовки мужские крутые'"
      :price="5000"
      :is-added="false"
      :is-favorite="false"
      :onClickAdd="onClickAdd"
    />
  </div>
</template>
<script setup>
import Card from './Card.vue'
const onClickAdd = () => {
  alert('Hi')
}
</script>
