<template>
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-2xl mt-14">
    <!-- <Drawer /> -->
    <Header />

    <div class="p-10">
      <div class="flex justify-between">
        <h2 class="text-3xl font-bold mb-8">Все кроссовки</h2>
      </div>

      <CardList />
    </div>
  </div>
</template>

<script setup>
import Header from './components/Head.vue'
import CardList from './components/CardList.vue'
</script>

<style lang="scss" scoped></style>
