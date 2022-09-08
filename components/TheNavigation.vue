<template>
  <v-app-bar max-height="64">
    <NuxtLink to="/" class="d-flex align-center">
      <v-img src="image/logo.png" width="100"></v-img>
    </NuxtLink>
    <v-row class="title" justify-space-around>
      <v-col cols="3">
        <NuxtLink to="/" style="text-decoration: none; color: white">
          <div>Home</div>
        </NuxtLink>
      </v-col>
      <v-col cols="3">
        <NuxtLink to="/contact" style="text-decoration: none; color: white">
          <div>Contact</div>
        </NuxtLink>
      </v-col>
      <v-col cols="3">
        <NuxtLink to="about" style="text-decoration: none; color: white">
          <div>À propos</div>
        </NuxtLink>
      </v-col>
    </v-row>
    <div
      v-if="$route.name === 'index'"
      class="search d-flex align-center justify-end ml-auto"
    >
      <v-text-field
        v-model="search"
        hide-details="auto"
        dense
        placeholder="Search for a post"
        prepend-icon="mdi-magnify"
        outlined
        :append-icon="search.length ? 'mdi-close' : ''"
        @click:append="clearSearch"
      />
    </div>
  </v-app-bar>
</template>

<script>
export default {
  name: 'TheNavigation',

  computed: {
    search: {
      get() {
        return this.$store.state.query
      },
      set(value) {
        this.$store.commit('SET_QUERY', value)
      },
    },
  },
  methods: {
    clearSearch() {
      this.$store.commit('SET_QUERY', '')
    },
  },
}
</script>

<style scoped></style>
