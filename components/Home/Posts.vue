<template>
  <div
    class="
      fixed
      top-16
      bottom-20
      w-full
      flex flex-col
      pt-8
      gap-4
      text-xl
      overflow-x-hidden
      overflow-y-auto
    "
  >
    <HomePost v-for="url in computedUrls" :key="url.link" :url="url.link" />
  </div>
</template>

<script>
export default {
  name: "Posts",
  props: {
    computedUrls: Array
  },
}
</script>

<style></style>
