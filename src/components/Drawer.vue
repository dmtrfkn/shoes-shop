<script setup>
import DrawerTitle from './DrawerTitle.vue'
import CartItemList from './CartItemList.vue'
</script>

<template>
  <div class="fixed top-0 left-0 h-full w-full bg-black z-10 opacity-70"></div>
  <div class="bg-white fixed w-96 h-full right-0 top-0 z-20 p-8">
    <DrawerTitle />

    <CartItemList />

    <div class="flex flex-col gap-5 mt-7">
      <div class="flex gap-2">
        <span>Итого:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>12900 R.</b>
      </div>

      <div class="flex gap-2">
        <span>Налог 5%:</span>
        <div class="flex-1 border-b border-dashed"></div>
        <b>900 R.</b>
      </div>

      <button
        disabled="true"
        class="mt-4 bg-lime-500 cursor-pointer w-full rounded-xl py-3 text-white transition disabled:bg-slate-400 hover:bg-lime-600 active:bg-lime-700"
      >
        Оформить
      </button>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
