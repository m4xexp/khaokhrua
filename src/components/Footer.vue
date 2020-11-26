<template>
  <v-card color="grey darken-4" height="150">
    <v-footer color="grey darken-4" padless absolute>
      <v-row justify="left" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link"
          color="white"
          text
          rounded
          class="my-2"
        >
          {{ link }}
        </v-btn>

        <v-spacer></v-spacer>

        <v-btn color="white" text rounded class="my-2" v-on:click="n+1">Back to top</v-btn>
        <v-col class="grey darken-4 text-center white--text" cols="12" style="margin: 15px auto">
          {{ new Date().getFullYear() }} — <strong>Khao Krua</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    links: [
      "All Categlory",
      "About Us",
      "Team",
      "Services",
      "Blog",
      "Contact Us",
    ],
  }),
};
</script>