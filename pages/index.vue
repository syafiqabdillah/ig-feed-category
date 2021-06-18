<template>
  <div class="relative flex w-screen max-h-screen">
    <HomeTitleBar :title="selectedCat" />
    <HomePosts :computedUrls="computedUrls" v-if="currentPage === 'posts'" />
    <HomeSetting v-if="currentPage === 'setting'" />
    <HomeCategories
      :selectedCat="selectedCat"
      :categories="categories"
      :chooseCategory="chooseCategory"
      :goToSetting="goToSetting"
    />
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      cats: ['All'],
      selectedCat: 'All',
      currentPage: 'posts',
      urls: [
        {
          link: 'https://www.instagram.com/p/CPcyUljhAg1/',
          category: 'Food',
        },
        {
          link: 'https://www.instagram.com/p/CPepQFQBwQ3/',
          category: 'Snack',
        },
        {
          link: 'https://www.instagram.com/p/CPXviMqB_JV/',
          category: 'Drink',
        },
        {
          link: 'https://www.instagram.com/p/COwHEKMhCCZ/',
          category: 'Appetizer',
        },
      ],
    }
  },
  computed: {
    categories() {
      var cats = new Set(this.cats)
      this.urls.forEach((url) => {
        cats.add(url.category)
      })
      return Array.from(cats)
    },
    computedUrls() {
      if (this.selectedCat === 'All') return this.urls
      return this.urls.filter((url) => {
        return url.category === this.selectedCat
      })
    },
  },
  mounted() {
    const category = this.$route.query.category
    if (category && this.categories.includes(category)) {
      this.selectedCat = category
    }
  },
  methods: {
    chooseCategory(cat) {
      this.currentPage = 'posts'
      this.selectedCat = cat
      window.scrollTo(0, 0)
    },
    goToSetting() {
      this.currentPage = 'setting'
      this.selectedCat = 'setting'
    },
  },
}
</script>

<style></style>
