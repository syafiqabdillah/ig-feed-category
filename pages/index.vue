<template>
  <div class="py-16 min-h-screen">
    <div class="flex flex-wrap justify-center gap-4 text-center text-xl">
      <HomePost v-for="url in computedUrls" :key="url.link" :url="url.link" />
    </div>
    <HomeCategories
      :selectedCat="selectedCat"
      :categories="categories"
      :chooseCategory="chooseCategory"
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
      this.selectedCat = cat
    },
  },
}
</script>

<style></style>
