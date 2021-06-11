<template>
  <div
    class="
      flex
      sm:justify-start
      md:justify-center
      gap-4
      flex-nowrap
      p-4
      h-20
      overflow-x-auto
      fixed
      bottom-0
      left-0
      w-full
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
        rounded-lg
        cursor-pointer
        hover:bg-green-400
        hover:text-white
        text-center
        flex-auto
        flex
        justify-center
        items-center
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
