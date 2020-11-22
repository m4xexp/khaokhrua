<template>
  <v-container class="container">
    <v-row align-content="center">
      <v-col cols="12" sm="6" md="6">
        <v-text-field
          value="Beef Wellington"
          label="ทำอะไรกินดีน้า"
          solo
        ></v-text-field>
      </v-col>
      <v-col md="6">
        <div class="searh_reciept_icon">
          <v-btn large color="red darken-1">
            <v-icon large color="white" alt="searchRecipt">search</v-icon>
          </v-btn>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<style>
.container {
  margin: 0% auto;
  max-width: 1200px;
  justify-content: center;
}
</style>