<template>
  <v-app>
    <Nav v-if="false"/>
    <Nav2 v-if="false"/>
    <v-content style="background-color: grey;">
      <Test />
      <SearchReceipt />
      <Home />
    </v-content>
    <Footer />
  </v-app>
</template>

<style>

</style>

<script>
import Nav from "./components/Nav";
import Nav2 from "./components/Nav2";
import Home from "./views/Home";
import Footer from "./components/Footer";
// import Test from "./views/Test";

export default {
  name: "App",

  components: {
    Home,
    Nav,
    Nav2,
    Footer,
    // Test,
  },

  data: () => ({
    //
  }),
};
</script>
