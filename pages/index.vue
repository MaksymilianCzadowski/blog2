<template>
  <v-container fluid>
    <div class="intro mt-5 mb-8">
      <h1 class="text-h1">Maks Codes Blog</h1>
      <h2 class="mt-2">the name of the blog is to be found</h2>
    </div>

    <v-row v-if="!posts.length">
      <v-col cols="12">
        <p>No post found, yet</p>
      </v-col>
    </v-row>

    <v-row v-else class="posts-container">
      <v-col cols="12">
        <div class="filter">
          <v-select
            v-if="categories.length"
            v-model="category"
            style="width: 100px"
            outlined
            dense
            hide-details="auto"
            :items="categories"
          />
        </div>
      </v-col>
      <v-col v-for="post in posts" :key="post.slug" cols="12" md="6">
        <v-card elevation="0">
          <v-card-title>
            {{ post.title }}
          </v-card-title>
          <v-card-text>
            <nuxt-content :document="{ body: post.excerpt }" />
          </v-card-text>
          <v-card-actions>
            <v-btn text :to="post.path"> Read More </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-row v-if="posts.length" class="post-paination">
      <v-col cols="12" class="text-right">
        <v-btn :disabled="page === 1" @click="fetchPrevious">
          <v-icon small>mdi-arrow-left</v-icon>
          Previous
        </v-btn>
        <v-btn :disabled="!fetchNext" @click="fetchNext">
          Next
          <v-icon small>mdi-arrow-right</v-icon>
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HomePage',
  layout: 'BlogDefault',
  async asyncData({ $content }) {
    const limit = 5
    const page = 1

    const fetchedPosts = await $content()
      .limit(limit)
      .sortBy('createdAt', 'desc')
      .skip((limit - 1) * (page - 1))
      .fetch()

    const nextPage = fetchedPosts.length === limit
    const posts = nextPage ? fetchedPosts.slice(0, -1) : fetchedPosts

    return {
      page,
      limit,
      posts,
      nextPage,
    }
  },
  data() {
    return {
      category: 'all',
      categories: [],
    }
  },

  fetch() {
    this.$content()
      .only(['category'])
      .fetch()
      .then((categories) => {
        const payload = Array.from(new Set(categories.map((c) => c.category)))
        this.categories = ['all', ...payload]
      })
  },

  computed: {
    searchQuery() {
      return this.$store.state.query
    },
  },
  watch: {
    async searchQuery(newValue) {
      this.page = 1
      await this.fetchPosts(newValue)
    },
    async category() {
      this.page = 1
      await this.fetchPosts(this.searchQuery)
    },
  },
  methods: {
    async fetchNext() {
      this.page += 1
      await this.fetchPosts()
    },
    async fetchPrevious() {
      this.page -= 1
      await this.fetchPosts()
    },
    async fetchPosts(query = '') {
      let baseFetch = this.$content().limit(this.limit)

      if (this.category !== 'all') {
        baseFetch = baseFetch.where({ category: this.category })
      }

      const fetchedPosts = await baseFetch
        .search(query)
        .skip((this.limit - 1) * (this.page - 1))
        .fetch()

      this.nextPage = fetchedPosts.length === this.limit
      const posts = this.nextPage ? fetchedPosts.slice(0, -1) : fetchedPosts

      this.posts = posts
    },
  },
}
</script>

<style lang="scss" scoped></style>
