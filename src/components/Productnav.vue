<template>
  <div id="app">
    <div class="text-h3 font-weight-bold py-16" align="center">
      OUR PRODUCTS
    </div>

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
        { title: "All Products", to: this.getTabPath("ourproducts") },
        { title: "Best Sellers", to: this.getTabPath("") },
        { title: "New Arrivals", to: this.getTabPath("") },
        { title: "Today Deals", to: this.getTabPath("") },
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
