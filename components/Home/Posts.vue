<template>
  <div
    class="
      pt-24
      pb-20
      w-full
      h-full
      flex flex-col
      justify-center
      items-center
      gap-4
      text-center text-xl
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
  watch: {
    computedUrls() {
      console.log('ay')
    }
  }
}
</script>

<style></style>
