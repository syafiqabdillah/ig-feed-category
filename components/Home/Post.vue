<template>
  <div>
    <HomeEmbeddedPost
      :class="{
        hidden: !showCaption,
      }"
      :showCaption="true"
      :url="url"
    />
    <HomeEmbeddedPost
      :class="{
        hidden: showCaption,
      }"
      :showCaption="false"
      :url="url"
    />
    <!-- Toggle -->
    <div class="text-base text-center cursor-pointer" @click="toggleCaption">
      {{ showCaption ? 'hide' : 'show' }} caption
    </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
  data() {
    return {
      showCaption: false,
      show: true,
    }
  },
  methods: {
    toggleCaption() {
      this.showCaption = !this.showCaption
    },
  },
  props: {
    url: String,
  },
}
</script>

<style></style>
