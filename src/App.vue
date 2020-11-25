<template>
  <v-app>
    <Nav v-if="false"/>
    <Nav2 v-if="true"/>
    <v-content style="background-color: #e4e5e5;">
      <Test />
      <SearchReceipt />
      <Home v-if="true"/>
    </v-content>
    <Footer />
  </v-app>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Kanit:wght@200&display=swap');

  *{
    font-family: 'Kanit', sans-serif;
  }

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
