<template>
  <v-app>

      <Nav2 v-if="true" />

    <v-main style="background-color: #e4e5e5">
      <Home v-if="true" />
    </v-main>

      <Footer />
  </v-app>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Kanit:wght@200&display=swap");

* {
  font-family: "Kanit", sans-serif;
}
</style>

<script>
// import Nav from "./components/Nav";
import Nav2 from "./components/Nav2";
import Home from "./views/Home";
import Footer from "./components/Footer";

export default {
  name: "App",

  components: {
    Home,
    // Nav,
    Nav2,
    Footer,
    // Test,
  },

  data: () => ({
    //
  }),
};
</script>
