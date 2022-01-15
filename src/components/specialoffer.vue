<template>
  <div>
    <div class="text-h3 font-weight-bold py-16" align="center">
      SPECIAL OFFER
    </div>

    <v-layout row wrap>
      <v-flex xs12 md6>
        <v-card class="mx-auto">
          <v-img
            src="https://essentialhome.eu/images/products/thumbnails/ambiances/bardot-armchair.png"
            height="300px"
            ><div class="text-overline text-right">
              <v-btn color="#26c6da">40% Off</v-btn>
            </div></v-img
          >
        </v-card>
      </v-flex>

      <v-flex xs12 md6>
        <v-card class="mx-auto">
          <v-img
            src="https://essentialhome.eu/images/products/thumbnails/ambiances/russel-armchair.png"
            height="300px"
            ><div class="text-overline text-right">
              <v-btn color="#26c6da">50% Off</v-btn>
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
