<template>
  <v-row class="d-flex justify-end align-end flex-column">
    <v-dialog v-model="dialog" width="600px">
      <template v-slot:activator="{ on, attrs }">
        <v-hover v-slot="{ hover }">
          <v-img
            class="image-pointer"
            :elevation="hover ? 12 : 2"
            v-bind="attrs"
            v-on="on"
            contain
            max-height="48"
            max-width="48"
            src="../assets/beerIcon.png"
          ></v-img>
        </v-hover>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">{{ item.name }}</span>
        </v-card-title>
        <v-img
          contain
          class="mx-auto pb-6"
          v-bind:src="item.image_url"
          max-height="400"
          max-width="100"
        ></v-img>
        <v-card-text>
          {{ item.description }}
          <p></p>
          <p><strong>ABV:</strong> {{ item.abv }}</p>
          <p><strong>IBU:</strong> {{ item.ibu }}</p>
          <p><strong>pH:</strong> {{ item.ph }}</p>
          <p><strong>EBC:</strong> {{ item.ebc }}</p>
          <p><strong>SRM:</strong> {{ item.srm }}</p>
          <p><strong>Attenuation level: </strong>{{ item.attenuation_level }}</p>
          <p><strong>Brewers tips:</strong> {{ item.brewers_tips }}</p>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="blue darken-1" text @click="dialog = false">
            Close
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
export default {
  props: ["item"],
  data() {
    return {
      dialog: false,
    };
  },
};
</script>

<style>
.image-pointer:hover {
  cursor: pointer;
}
</style>