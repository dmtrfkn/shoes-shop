<template>
  <div class="bg-white w-4/5 m-auto rounded-xl shadow-2xl mt-14">
    <!-- <Drawer /> -->
    <Header />

    <div class="p-10">
      <div class="flex justify-between items-center">
        <h2 class="text-3xl font-bold mb-8">Все кроссовки</h2>

        <div class="flex gap-4">
          <select
            @change="onChangeSelect"
            name=""
            class="py-2 px-3 rounded-md border outline-none"
            id=""
          >
            <option value="title">По названию</option>
            <option value=" price">По цене (сначала дешевые)</option>
            <option value="-price">По цене (сначала дорогие)</option>
          </select>

          <div class="relative">
            <img class="absolute top-3 left-4" src="/search.svg" alt="Search " />
            <input
              @input="onChangeSearchInput"
              class="border rounded-md py-1.5 pl-11 pr-4 outline-none m-0 focus:border-gray-400"
              type="text"
              placeholder="Поиск..."
            />
          </div>
        </div>
      </div>

      <div class="mt- 10"><CardList :items="items" /></div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
<script setup>
import axios from 'axios'
import Header from './components/Head.vue'
import CardList from './components/CardList.vue'
import { onMounted, reactive, ref, watch } from 'vue'

const items = ref([])

const filters = reactive({
  sortBy: 'title',
  searchQuery: ''
})

const onChangeSelect = (event) => {
  filters.sortBy = event.target.value
}

const onChangeSearchInput = (event) => {
  filters.searchQuery = event.target.value
}

const fetchItems = async () => {
  try {
    const params = {
      sortBy: filters.sortBy
    }

    if (filters.searchQuery) {
      params.title = `*${filters.searchQuery}*`
    }

    items.value = (
      await axios.get(`https://80890f433358ae64.mokky.dev/items`, {
        params
      })
    ).data
    console.log(items)
  } catch (error) {
    console.warn(error)
  }
}

onMounted(fetchItems)

watch(filters, fetchItems)
</script>
