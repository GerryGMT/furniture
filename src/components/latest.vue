<template>
  <div>
    <div class="text-h3 font-weight-bold py-16" align="center">
      OUR LATEST ARTICLES
    </div>

    <v-layout row wrap>
      <v-flex xs12 md6>
        <v-card class="mx-auto">
          <v-img
            src="https://www.epichomeideas.com/wp-content/uploads/2016/10/shutterstock_315930389.jpg"
            height="200px"
            ><div class="text-overline">
              <v-btn color="#26c6da">New</v-btn>
            </div></v-img
          >
        </v-card>
      </v-flex>

      <v-flex xs12 md6>
        <v-card class="mx-auto">
          <v-img
            src="https://essentialhome.eu/images/products/thumbnails/ambiances/bardot-armchair.png"
            height="200px"
            ><div class="text-overline">
              <v-btn color="#26c6da">New</v-btn>
            </div></v-img
          >
        </v-card>
      </v-flex>
    </v-layout>

    <v-layout row wrap>
      <v-flex xs12 md6>
        <v-card class="mx-auto">
          <v-img
            src="https://essentialhome.eu/images/products/thumbnails/ambiances/loren-armchair.png"
            height="200px"
            ><div class="text-overline">
              <v-btn color="#26c6da">New</v-btn>
            </div></v-img
          >
        </v-card>
      </v-flex>

      <v-flex xs12 md6>
        <v-card class="mx-auto">
          <v-img
            src="https://www.epichomeideas.com/wp-content/uploads/2016/10/daybed-sofa.jpg"
            height="200px"
            ><div class="text-overline">
              <v-btn color="#26c6da">New</v-btn>
            </div></v-img
          >
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style>
.title {
  color: #000;
}
</style>
