<template>
  <div class="w-full flex justify-center">
    <div :class="{ hidden: !show }">
      <HomeEmbeddedPost
        :class="{
          hidden: !showCaption,
        }"
        :showCaption="true"
        :show="show"
        :setShow="setShow"
        :url="url"
      />
      <HomeEmbeddedPost
        :class="{
          hidden: showCaption,
        }"
        :showCaption="false"
        :setShow="setShow"
        :show="show"
        :url="url"
      />
      <!-- Toggle -->
      <div
        class="text-base text-center cursor-pointer"
        @click="toggleCaption"
        v-if="show"
      >
        {{ showCaption ? 'hide' : 'show' }} caption
      </div>
    </div>
    <Loading :class="{ hidden: show }">Loading...</Loading>
  </div>
</template>

<script>
export default {
  name: 'Post',
  props: {
    url: String,
  },
  data() {
    return {
      showCaption: false,
      show: false,
    }
  },
  methods: {
    toggleCaption() {
      this.showCaption = !this.showCaption
    },
    setShow(isShow) {
      this.show = isShow
    },
  },
  mounted() {
    this.setShow(false)
    setTimeout(() => this.setShow(true), 2000)
  },
}
</script>

<style></style>
