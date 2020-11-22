<template>
  <v-app>
    <Nav />
    <v-content>
      <SearchReceipt />
      <Home />
    </v-content>
    <Footer />
  </v-app>
</template>

<style>
template v-app v-content {
  align-content: center;
}
</style>

<script>
import Nav from "./components/Nav";
import Home from "./views/Home";
import Footer from "./components/Footer";

export default {
  name: "App",

  components: {
    Home,
    Nav,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
