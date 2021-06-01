<template>
  <div>
    <!-- With Caption -->
    <div :class="{ hidden: !useCaption }">
      <HomeCaptionPost :url="url" />
    </div>
    <!-- Without Caption -->
    <div :class="{ hidden: useCaption }">
      <HomeNoCaptionPost :url="url" />
    </div>
    <!-- Toggle -->
    <div class="text-center cursor-pointer" @click="toggleCaption">
      {{ useCaption ? 'hide' : 'show' }} caption
    </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
  data() {
    return {
      useCaption: false,
      show: true,
    }
  },
  methods: {
    toggleCaption() {
      this.useCaption = !this.useCaption
    },
  },
  props: {
    url: String,
  },
}
</script>

<style></style>
