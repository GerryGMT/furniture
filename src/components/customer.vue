<template>
  <div>
    <div class="text-h3 font-weight-bold py-16" align="center">
      WHAT OUR CUSTOMER SAYS
    </div>

    <div class="carousel">
      <v-carousel
        v-model="carousel"
        cycle
        height="400"
        hide-delimiters
        show-arrows-on-hover
      >
        <v-carousel-item>
          <v-card class="mx-auto" max-width="400" align="center">
            <v-list-item-avatar color="grey darken-3">
              <v-img
                class="elevation-6"
                alt=""
                src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
              ></v-img>
            </v-list-item-avatar>

            <v-card-text class="text-h5 font-weight-bold">
              "Turns out semicolon-less style is easier and safer in TS because
              most gotcha edge cases are type invalid as well."
            </v-card-text>

            <v-card-actions>
              <v-list-item class="grow">
                <v-list-item-content align="center">
                  <v-list-item-title>Angelina Joly</v-list-item-title>
                  <v-list-item-subtitle>co-founder</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-card-actions>
          </v-card>
        </v-carousel-item>

        <v-carousel-item>
          <v-card class="mx-auto" dark max-width="400" align="center">
            <v-list-item-avatar color="grey darken-3">
              <v-img
                class="elevation-6"
                alt=""
                src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
              ></v-img>
            </v-list-item-avatar>

            <v-card-text class="text-h5 font-weight-bold">
              "Turns out semicolon-less style is easier and safer in TS because
              most gotcha edge cases are type invalid as well."
            </v-card-text>

            <v-card-actions>
              <v-list-item class="grow">
                <v-list-item-content align="center">
                  <v-list-item-title>Angelina Joly</v-list-item-title>
                  <v-list-item-subtitle>co-founder</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-card-actions>
          </v-card>
        </v-carousel-item>

        <v-carousel-item>
          <v-card
            class="mx-auto"
            color="#26c6da"
            max-width="400"
            align="center"
          >
            <v-list-item-avatar color="grey darken-3">
              <v-img
                class="elevation-6"
                alt=""
                src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light"
              ></v-img>
            </v-list-item-avatar>

            <v-card-text class="text-h5 font-weight-bold">
              "Turns out semicolon-less style is easier and safer in TS because
              most gotcha edge cases are type invalid as well."
            </v-card-text>

            <v-card-actions>
              <v-list-item class="grow">
                <v-list-item-content align="center">
                  <v-list-item-title>Angelina Joly</v-list-item-title>
                  <v-list-item-subtitle>co-founder</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-card-actions>
          </v-card>
        </v-carousel-item>
      </v-carousel>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      carousel: 0,
    };
  },
};
</script>

<style></style>
