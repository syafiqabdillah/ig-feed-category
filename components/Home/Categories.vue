<template>
  <div class="flex justify-center gap-4">
    <div
      :class="{
        'bg-green-400': category === selectedCat,
        'text-white': category === selectedCat,
      }"
      class="
        my-8
        p-4
        rounded-lg
        cursor-pointer
        hover:bg-green-400
        hover:text-white
        flex-auto
        text-center
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
