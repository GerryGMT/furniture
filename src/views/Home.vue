<template>
  <v-app id="lux">
    <div>
      <v-app-bar>
        <v-toolbar-title class="font-weight-bold"
          >Genesis Furniture</v-toolbar-title
        >
        <v-spacer></v-spacer>
        <v-text-field
          color="green"
          @focus="SearchClosed = false"
          @blur="SearchClosed = true"
          placeholder="Search"
          prepend-inner-icon="mdi-magnify"
          class="expanding-search mt-6"
          :class="{ closed: SearchClosed }"
          filled
          dense
        ></v-text-field>
        <v-btn icon>
          <v-icon>mdi-shopping-outline</v-icon>
        </v-btn>
      </v-app-bar>

      <v-toolbar flat>
        <div align="center">
          <v-list class="d-flex align-center">
            <v-btn color="green" dark
              ><v-icon>mdi-filter-variant</v-icon>All collections</v-btn
            >
            <v-spacer></v-spacer>
            <v-list-item link v-for="(menu, m) in menus" :key="m" to="route">
              <v-list-item-content>
                <v-list-item-title class="text-h7">
                  {{ menu.title }}
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </div>
      </v-toolbar>
    </div>

    <v-container grid-list-md text-xs-center>
      <v-layout row wrap>
        <v-flex xs12 md3>
          <v-card class="mx-auto" width="256" tile>
            <v-list>
              <v-list-group
                v-if="mobile"
                :value="false"
                prepend-icon="mdi-expand-all-outline"
                no-action
              >
                <template v-slot:activator>
                  <v-list-item-content>
                    <v-list-item-title>All</v-list-item-title>
                  </v-list-item-content>
                </template>

                <v-list-item v-for="([title], i) in cruds" :key="i" link>
                  <v-list-item-title v-text="title"></v-list-item-title>
                </v-list-item>
              </v-list-group>

              <v-list-group
                v-else
                :value="true"
                prepend-icon="mdi-expand-all-outline"
                no-action
              >
                <template v-slot:activator>
                  <v-list-item-content>
                    <v-list-item-title>All</v-list-item-title>
                  </v-list-item-content>
                </template>

                <v-list-item v-for="([title], i) in cruds" :key="i" link>
                  <v-list-item-title v-text="title"></v-list-item-title>
                </v-list-item>
              </v-list-group>
            </v-list>
          </v-card>
        </v-flex>

        <v-flex xs12 md9>
          <!-- Carousel -->
          <div class="carousel">
            <v-carousel
              v-model="carousel"
              cycle
              hide-delimiter-background
              show-arrows-on-hover
            >
              <v-carousel-item>
                <v-sheet height="100%">
                  <v-row class="fill-height" align="center" justify="center">
                    <v-img
                      src="https://www.epichomeideas.com/wp-content/uploads/2016/10/chesterfield-sofa.jpg"
                    ></v-img>
                  </v-row>
                </v-sheet>
              </v-carousel-item>
              <v-carousel-item>
                <v-sheet height="100%">
                  <v-row class="fill-height" align="center" justify="center">
                    <v-img
                      src="https://www.epichomeideas.com/wp-content/uploads/2016/10/shutterstock_315930389.jpg"
                    ></v-img>
                  </v-row>
                </v-sheet>
              </v-carousel-item>
              <v-carousel-item>
                <v-sheet height="100%">
                  <v-row class="fill-height" align="center" justify="center">
                    <v-img
                      src="https://www.epichomeideas.com/wp-content/uploads/2016/10/sectional-sofa.jpg"
                    ></v-img>
                  </v-row>
                </v-sheet>
              </v-carousel-item>
              <v-carousel-item>
                <v-sheet height="100%">
                  <v-row class="fill-height" align="center" justify="center">
                    <v-img
                      src="https://www.epichomeideas.com/wp-content/uploads/2016/10/daybed-sofa.jpg"
                    ></v-img>
                  </v-row>
                </v-sheet>
              </v-carousel-item>
            </v-carousel>
          </div>
        </v-flex>

        <v-flex xs12 md3>
          <v-card>
            <v-list-item>
              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="text-h5">
                  Free Shipping
                </v-list-item-title>
                <v-list-item-subtitle>Orders over $100</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-flex>

        <v-flex xs12 md3>
          <v-card>
            <v-list-item>
              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="text-h5">
                  Smart Gift Card
                </v-list-item-title>
                <v-list-item-subtitle
                  >Buy $1000 to get card</v-list-item-subtitle
                >
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-flex>

        <v-flex xs12 md3>
          <v-card>
            <v-list-item>
              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="text-h5">
                  Quick Payment
                </v-list-item-title>
                <v-list-item-subtitle>100% secure payment</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-flex>

        <v-flex xs12 md3>
          <v-card>
            <v-list-item>
              <v-list-item-avatar
                tile
                size="80"
                color="grey"
              ></v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title class="text-h5">
                  24/7 Support
                </v-list-item-title>
                <v-list-item-subtitle>Quick support</v-list-item-subtitle>
              </v-list-item-content>
            </v-list-item>
          </v-card>
        </v-flex>

        <v-flex d-flex xs12 sm6 md6>
          <v-card class="mx-auto" height="400">
            <v-img
              src="https://www.epichomeideas.com/wp-content/uploads/2016/10/sectional-sofa.jpg"
              height="400px"
            >
            </v-img>
          </v-card>
        </v-flex>

        <v-flex d-flex xs12 sm6 md6>
          <v-layout row wrap>
            <v-flex d-flex>
              <v-card class="mx-auto" height="200">
                <v-img
                  src="https://www.epichomeideas.com/wp-content/uploads/2016/10/chesterfield-sofa.jpg"
                  height="200px"
                ></v-img>
              </v-card>
            </v-flex>

            <v-flex d-flex>
              <v-card class="mx-auto" height="200">
                <v-img
                  src="https://www.epichomeideas.com/wp-content/uploads/2016/10/daybed-sofa.jpg"
                  height="200px"
                ></v-img>
              </v-card>
            </v-flex>
          </v-layout>
        </v-flex>
      </v-layout>

      <navbar />
      <trending />
      <specialoffer />
      <productnav />
      <ourproducts />
      <customer />
      <latest />

      <v-layout row wrap class="pa-10">
        <v-flex xs12 md3>
          <div class="font-weight-bold">Funking</div>
          <div>
            is the popular Ecommerce site. Lorem, ipsum dolor sit amet
            consectetur adipisicing elit. Aspernatur voluptatem et tempore
            aperiam.
          </div>
          <div>
            <v-icon class="pa-2">mdi-facebook</v-icon>
            <v-icon class="pa-2">mdi-twitter</v-icon>
            <v-icon class="pa-2">mdi-instagram</v-icon>
            <v-icon class="pa-2">mdi-pinterest</v-icon>
          </div>
        </v-flex>

        <v-flex xs12 md3>
          <v-list-item>
            <v-list-item-content>
              <div class="font-weight-bold">Help</div>
              <div>Privacy Policy</div>
              <div>Shipping & delivery</div>
              <div>Refund Policy</div>
              <div>Track your order</div>
            </v-list-item-content>
          </v-list-item>
        </v-flex>

        <v-flex xs12 md3>
          <v-list-item>
            <v-list-item-content>
              <div class="font-weight-bold">Store</div>
              <div>Furniture</div>
              <div>Table</div>
              <div>Sofa</div>
              <div>Other</div>
            </v-list-item-content>
          </v-list-item>
        </v-flex>

        <v-flex xs12 md3>
          <v-list-item>
            <v-list-item-content>
              <div class="font-weight-bold">Support</div>
              <div>Feedback</div>
              <div>Contact Us</div>
              <div>Download App</div>
              <div>Terms and Condition</div>
            </v-list-item-content>
          </v-list-item>
        </v-flex>
      </v-layout>
    </v-container>

    <v-footer>
      <v-card-title>
        <v-icon x-small>mdi-copyright</v-icon>
        {{ new Date().getFullYear() }} Funking - All rights reserved.
      </v-card-title>
      <v-spacer></v-spacer>
      <div>
        <strong class="subheading pa-2">Privacy</strong>
        <strong class="subheading pa-2">Security</strong>
        <strong class="subheading pa-2">Terms</strong>
      </div>
    </v-footer>
  </v-app>
</template>

<script>
import Customer from "../components/customer.vue";
import Latest from "../components/latest.vue";
import Navbar from "../components/Navbar.vue";
import Ourproducts from "../components/ourproducts.vue";
import Productnav from "../components/Productnav.vue";
import Specialoffer from "../components/specialoffer.vue";
import Trending from "../components/trending.vue";
export default {
  components: {
    Navbar,
    Trending,
    Specialoffer,
    Productnav,
    Ourproducts,
    Customer,
    Latest,
  },
  data() {
    return {
      value: false,
      SearchClosed: true,
      carousel: 0,
      selectedCollection: 0,
      menus: [{ title: "Contact Us" }],
      cruds: [
        ["New Arrivals"],
        ["Hot Sale"],
        ["Furniture"],
        ["Amrature"],
        ["Table"],
        ["Chair"],
        ["Sofa"],
        ["Mirrors"],
        ["Stools"],
        ["Benches"],
      ],
    };
  },
  computed: {
    mobile() {
      return this.$vuetify.breakpoint.smAndDown;
    },
  },
};
</script>

<style scoped>
span {
  color: #fff;
}
.expanding-search {
  transition: 0.4s;
}
.closed {
  max-width: 45px;
}
.v-input__slot {
  background: transparent !important;
}
</style>
