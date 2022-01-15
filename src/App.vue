<template>
  <v-app>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data() {
    return {
      menus: [
        { title: "Home", route: "home" },
        { title: "Home" },
        { title: "Home" },
        { title: "Home" },
        { title: "Home" },
      ],
    };
  },
};
</script>
