<template>
  <v-app>
    <v-app-bar
      app
      color="rgba(194, 158, 80, 1)"
      src="./assets/BrewDogBanner2.png"
      height="140"
      shrink-on-scroll
      dark
      dense
      elevate-on-scroll
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-2"
    >
      <template v-slot:img="{ props }">
        <v-img v-bind="props"></v-img>
      </template>

      <v-spacer></v-spacer>

      <v-btn href="https://www.brewdog.com/uk/" target="_blank" text>
        <span>Brewdog Website</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>
    <v-sheet
      id="scrolling-techniques-2"
      class="overflow-y-auto"
      max-height="100vh"
    >
      <v-main class="cyan accent-4">
        <Home />
      </v-main>
    </v-sheet>
  </v-app>
</template>

<script>
import Home from "./components/Home";

export default {
  //hide global window scrollbar, since we scroll the v-sheet content only
  mounted: function() {
    let elHtml = document.getElementsByTagName('html')[0]
    elHtml.style.overflowY = 'hidden'
  },
  destroyed: function() {
    let elHtml = document.getElementsByTagName('html')[0]
    elHtml.style.overflowY = null
  },

  name: "App",

  components: {
    Home,
  },

  data: () => ({
    //
  }),
};

</script>

