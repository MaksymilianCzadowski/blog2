<template>
  <v-app>
    <!-- Navigation -->
    <TheNavigation />
    <v-main>
      <v-container>
        <v-row>
          <v-col cols="12" md="10">
            <Nuxt />
          </v-col>
          <v-col cols="12" md="2">
            <!-- Ads / side content -->
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'BlogDefault',

  data() {
    return {

    };
  },

  mounted() {

  },

  methods: {

  },
};
</script>

<style lang="scss" scoped>

</style>
