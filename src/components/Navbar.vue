<template>
  <div id="app">
    <div class="text-h3 font-weight-bold py-16" align="center">TRENDING</div>
    <v-card class="tab">
      <v-tabs center-active fixed-tabs>
        <v-tab v-for="item in items" :key="item.title" :to="item.to">
          {{ item.title }}
        </v-tab>
        <v-tabs-items @change="updateRouter($event)" touchless>
          <v-tab-item v-for="item in items" :key="item.title" :value="item.to">
            <router-view />
          </v-tab-item>
        </v-tabs-items>
      </v-tabs>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { title: "Top Products", to: this.getTabPath("trending") },
        { title: "New Arrivals", to: this.getTabPath("") },
        { title: "Best Sellers", to: this.getTabPath("") },
      ],
    };
  },
  methods: {
    getTabPath(name) {
      return this.$router.resolve({ name, params: this.$route.params }).href;
    },
    updateRouter(path) {
      this.$router.push(path);
    },
  },
};
</script>

<style>
.Title {
  text-align: center;
}
</style>
