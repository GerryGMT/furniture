<template>
  <v-app id="lux">
    <div>
      <v-system-bar height="50" color="green" class="px-4 text-caption">
        <span>Welcome To Our Online Shop</span>
        <v-spacer></v-spacer>
        <span>English(USD)</span>
        <v-icon>mdi-chevron-down</v-icon>
        <v-divider vertical></v-divider>
        <v-btn text color="#fff">Login or Sign Up</v-btn>
      </v-system-bar>

      <v-app-bar>
        <v-toolbar-title class="font-weight-bold">Furniking</v-toolbar-title>
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
        <v-btn icon>
          <v-icon>mdi-bell-outline</v-icon>
        </v-btn>
        <v-btn icon>
          <v-icon>mdi-account-outline</v-icon>
        </v-btn>
      </v-app-bar>

      <v-toolbar flat>
        <div align="center">
          <v-spacer></v-spacer>
          <v-list class="d-flex align-center">
            <v-btn color="green" dark
              ><v-icon>mdi-filter-variant</v-icon>All collections</v-btn
            >
            <v-spacer></v-spacer>
            <v-list-item link v-for="(menu, m) in menus" :key="m" to="route">
              <v-list-item-content>
                <v-list-item-title class="text-h6 px-2">
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
            <v-navigation-drawer permanent>
              <v-divider></v-divider>
              <v-list nav dense>
                <v-list-item-group v-model="selectedCollection" color="primary">
                  <v-list-item v-for="(collection, c) in collections" :key="c">
                    <v-list-item-icon>
                      <v-icon v-text="collection.icon"></v-icon>
                    </v-list-item-icon>

                    <v-list-item-content>
                      <v-list-item-title
                        v-text="collection.text"
                      ></v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list-item-group>
              </v-list>
            </v-navigation-drawer>
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
      SearchClosed: true,
      carousel: 0,
      selectedCollection: 0,
      menus: [
        { title: "Home", route: "home" },
        { title: "Shop" },
        { title: "Blog" },
        { title: "About" },
        { title: "Contact Us" },
      ],
      collections: [
        { text: "All" },
        { text: "New Arrivals" },
        { text: "Hot Sale" },
        { text: "Furniture" },
        { text: "Amrature" },
        { text: "Table" },
        { text: "Chair" },
        { text: "Sofa" },
        { text: "Mirrors" },
        { text: "Stools" },
        { text: "Benches" },
      ],
      items: [
        { title: "Dashboard", icon: "mdi-view-dashboard" },
        { title: "Photos", icon: "mdi-image" },
        { title: "About", icon: "mdi-help-box" },
      ],
    };
  },
};
</script>

<style scoped>
.carousel {
  color: #000;
}
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
