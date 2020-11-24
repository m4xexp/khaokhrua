<template>
  <v-container class="container">
        <v-text-field
          style="width:600px"
          value="Beef Wellington"
          label="ทำอะไรกินดีน้า"
          solo
        ></v-text-field>
          <v-btn large color="red darken-1">
            <v-icon large color="white" alt="searchRecipt">search</v-icon>
          </v-btn>
  </v-container>
</template>

<style>
.container {
  margin: 0% auto;
  max-width: 1200px;
  justify-content: center;
}
</style>