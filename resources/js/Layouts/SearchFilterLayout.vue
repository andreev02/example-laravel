<script setup>
defineProps({
  filters: {
    type: Object,
  },
});
</script>

<template>
  <div class="mb-2.5 flex items-center">
    <form class="flex flex-col md:flex-row gap-3">
      <div class="flex">
        <input v-model="filters.search" type="text" name="search" placeholder="Search for the tool you like"
          class="w-full md:w-80 px-3 h-10 rounded-l border-2 border-sky-500 focus:outline-none focus:border-sky-500">
        <button type="submit" class="bg-sky-500 text-white rounded-r px-2 md:px-3 py-0 md:py-1">Search</button>
      </div>
      <select v-model="filters.trashed" name="trashed"
        class="w-full h-10 border-2 border-sky-500 focus:outline-none focus:border-sky-500 text-sky-500 rounded px-2 md:px-3 py-0 md:py-1 tracking-wider">
        <option :value="null"> </option>
        <option value="with">With Trashed</option>
        <option value="only">Only Trashed</option>
      </select>
    </form>
  </div>
</template>