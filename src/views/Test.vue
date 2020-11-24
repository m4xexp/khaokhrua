<template>
  <v-container class="grey lighten-5">
    <v-btn style="justify-content: center;" color="accent">Hello</v-btn>
    <div class="ingrediants" style="align-text: center">
      <h1 style="text-align: center;">ส่วนผสม</h1>
      <h1 style="color: red;">555555555</h1>
      <v-divider></v-divider>
      <h2>ใส่ส่วนผสม</h2>
      <div class="frameoftextfield" style="border-style: double; width: 80%;">
          <v-text-field
            label="Outlined"
            placeholder="เช่น แป้งสาลี"
          ></v-text-field>
      </div>
      <h3>66666</h3>
    </div>
    <v-row no-gutters>
      <template v-for="n in 4">
        <v-col :key="n">
          <v-icon>home</v-icon>
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
        <v-responsive
          v-if="n === 2"
          :key="`width-${n}`"
          width="100%"
        ></v-responsive>
      </template>
    </v-row>
  </v-container>
</template>

<script>
export default {};
</script>

<style>
    .ingrediants{
        text-align: center;
    }
</style>