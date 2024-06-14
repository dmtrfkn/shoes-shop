<script setup>
import axios from 'axios'
import Header from './components/Head.vue'
import CardList from './components/CardList.vue'
import { onMounted, ref } from 'vue'

const items = ref([])

onMounted(async () => {
  try {
    items.value = (await axios.get('https://80890f433358ae64.mokky.dev/items')).data
    console.log(items)
  } catch (error) {
    console.warn(error)
  }
})
</script>

<template>
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-2xl mt-14">
    <!-- <Drawer /> -->
    <Header />

    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-8">Все кроссовки</h2>

        <div class="flex gap-4">
          <select name="" class="py-2 px-3 rounded-md border outline-none" id="">
            <option value="">По названию</option>
            <option value="">По цене (сначала дешевые)</option>
            <option value="">По цене (сначала дорогие)</option>
          </select>

          <div class="relative">
            <img class="absolute top-3 left-4" src="/search.svg" alt="Search " />
            <input
              class="border rounded-md py-1.5 pl-11 pr-4 outline-none m-0 focus:border-gray-400"
              type="text"
              placeholder="Поиск..."
            />
          </div>
        </div>
      </div>

      <div class="mt- 10">// <CardList :items="items" /></div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
