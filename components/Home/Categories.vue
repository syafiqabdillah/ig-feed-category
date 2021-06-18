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
      overflow-x-auto overflow-hidden
      fixed
      bottom-0
      left-0
      bg-white
      shadow
      w-screen
      z-10
    "
  >
    <div
      :class="{
        'bg-green-400': 'setting' === selectedCat,
        'text-white': 'setting' === selectedCat,
      }"
      class="
        rounded-lg
        cursor-pointer
        hover:bg-green-400
        hover:text-white
        text-center
        flex
        justify-center
        items-center
        px-4
      "
      @click.self="goToSetting()"
    >
      <i class="icofont-settings"></i>
    </div>
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
        flex-auto flex
        justify-center
        items-center
        px-4
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
    goToSetting: Function,
  },
}
</script>

<style></style>
