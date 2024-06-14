<script setup>
defineProps({
  imageUrl: String,
  title: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickAdd: Function,
  onClickFavorite: Function
})
</script>

<template>
  <div
    class="relative bg-white border border-slate-100 rounded-3xl p-8 transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      class="absolute top-8 left-8 cursor-pointer w-8 h-8 p-0 border rounded-lg hover:border-black"
      alt="Like 1"
      @click="onClickFavorite"
    />
    <img :src="imageUrl" alt="Sneaker" />
    <p class="mt-2">{{ title }}</p>
    <div class="flex justify-between">
      <div class="flex flex-col mt-5">
        <span class="text-slate-400">Цена</span>
        <b>{{ price }} руб.</b>
      </div>
      <img
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="Plus"
        @click="onClickAdd"
        class="cursor-pointer w-8 h-8 p-0 border rounded-lg hover:border-black"
      />
    </div>
  </div>
</template>
