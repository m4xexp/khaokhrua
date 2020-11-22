<template>
  <v-card class="grey lighten-4">
    <v-container class="white lighten-5">

      <div class="search_icon"><SearchReceipt /></div>

      <v-row class="mb-6" no-gutters>
        <v-col v-for="n in 5" :key="n">
          <v-card :loading="loading" class="mx-auto my-12" max-width="374">
            <template slot="progress">
              <v-progress-linear
                color="deep-purple"
                height="10"
                indeterminate
              ></v-progress-linear>
            </template>

            <v-img
              height="250"
              src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
            ></v-img>

            <v-card-title>Cafe Badilico</v-card-title>

            <v-card-text>
              <v-row align="center" class="mx-0">
                <v-rating
                  :value="4.5"
                  color="amber"
                  dense
                  half-increments
                  readonly
                  size="14"
                ></v-rating>
                
                <div class="grey--text ml-4">4.5 (413)</div>
              </v-row>

              <div class="my-4 subtitle-1">$ • Italian, Cafe</div>

              <div>
                Small plates, salads & sandwiches - an intimate setting with 12
                indoor seats plus patio seating.
              </div>
            </v-card-text>

            <v-divider class="mx-4"></v-divider>

            <v-card-title>Tonight's availability</v-card-title>

            <v-card-text>
              <v-chip-group
                v-model="selection"
                active-class="deep-purple accent-4 white--text"
                column
              >
                <v-chip>5:30PM</v-chip>

                <v-chip>7:30PM</v-chip>

                <v-chip>8:00PM</v-chip>

                <v-chip>9:00PM</v-chip>
              </v-chip-group>
            </v-card-text>

            <v-card-actions>
              <v-btn color="deep-purple lighten-2" text @click="reserve">
                Reserve
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
      <div style="position: relative; margin: auto;">
        <v-btn color="red darken-1 white--text">สูตรอาหารทั้งหมด</v-btn>
      </div>
    </v-container>
    <div>
      <Pagination />
    </div>
  </v-card>
</template>

<script>
import Pagination from "./Pagination.vue";
import SearchReceipt from "./SearchReceipt.vue";

export default {
  name: "Home",

  components: {
    Pagination,
    SearchReceipt,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
* {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

template v-card v-container div {
  align-content: center;
}
</style>

