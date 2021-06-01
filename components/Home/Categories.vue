<template>
  <div
    class="
      flex
      sm:justify-start
      md:justify-center
      gap-4
      flex-nowrap
      my-8
      overflow-x-auto
    "
  >
    <div
      :class="{
        'bg-green-400': category === selectedCat,
        'text-white': category === selectedCat,
      }"
      class="
        p-4
        rounded-lg
        cursor-pointer
        hover:bg-green-400
        hover:text-white
        flex-auto
        text-center
        block
      "
      v-for="category in categories"
      :key="category"
      @click="chooseCategory(category)"
    >
      {{ category }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Categories',
  props: {
    selectedCat: String,
    categories: Array,
    chooseCategory: Function,
  },
}
</script>

<style></style>
