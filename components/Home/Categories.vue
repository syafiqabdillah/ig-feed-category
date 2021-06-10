<template>
  <div
    class="
      flex
      sm:justify-start
      md:justify-center
      gap-4
      flex-nowrap
      py-4
      overflow-x-auto
      fixed
      bottom-0
      left-0
      w-full
      px-4
      bg-white
      shadow
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
