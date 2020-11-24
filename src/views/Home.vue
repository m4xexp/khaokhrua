<template>
  <div class="home-container">
    <div class="flex-header">
      <div class="header-menu-card-box">
        <div class="header-text">
          <h1 class="text-menu-suggest">เมนูเเนะนำสำหรับคุณ</h1>
        </div>
      </div>
      <div class="header-menu-tag" style="display: flex">
        <div class="btn-views-all-tag" style="display: flex">
          <h5>ดูทั้งหมด</h5>
          <v-icon>arrow_right_alt</v-icon>
        </div>

        <div
          class="menu-tag-box"
          style="
            background-color: blue;
            margin-top: 10px;
            margin-right: 20px;
            height: 50px;
            display: flex;
            position: absolute;
          "
        >
          <div class="menu-tag-cover" v-for="tag in tags" :key="tag.tagName">
            <v-chip
              link
              outlined
              class="ma-2"
              color="pink"
              label
              text-color="white"
            >
              <v-icon left> mdi-label </v-icon>
              {{ tag.tagName }}
            </v-chip>
          </div>
        </div>
      </div>
    </div>

    <div class="menu-card-box">
      <v-layout
        row
        wrap
        style="background-color: blue"
        class="menu-card-cober-each-card"
      >
        <v-flex
          xs12
          sm6
          md4
          lg3
          v-for="recipe in menus"
          :key="recipe.Name"
          class="menu-card-each-card"
        >
          <v-card :loading="loading" class="mx-auto" max-width="374">
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
            </v-card-text>

            <v-card-actions>
              <v-btn color="deep-purple lighten-2" text @click="reserve">
                Reserve
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </div>

    <div class="btn-see-all-receipt">
      <v-btn color="success">text</v-btn>
    </div>
    <div>
      <Pagination />
    </div>
  </div>
</template>

<script>
import Pagination from "./Pagination.vue";
// import SearchReceipt from "./SearchReceipt.vue";

export default {
  name: "Home",

  components: {
    Pagination,
    // SearchReceipt,
  },

  data: () => ({
    menus: [
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Tomyum Kung", Author: "KhaoKrua" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Tomyum Kung", Author: "KhaoKrua" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua" },
      { Name: "Tomyum Kung", Author: "KhaoKrua" },
    ],
    tags: [
      { tagName: "Drink" },
      { tagName: "Main Disc" },
      { tagName: "Burger" },
      { tagName: "Noodle" },
      { tagName: "Fruit" },
      { tagName: "Cheese" },
      { tagName: "Cream" },
    ],
  }),
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  outline: none;
  font-family: monospace;
}

.home-container{
  width: 90%;
  margin-left: 5rem;
  position: relative;
}

.flex-header {
  display: flex;
  justify-content: space-between;
  background-color: pink;
}

.menu-card-cober-each-card .menu-card-each-card {
  background-color: yellow;
  padding: 5px 5px 5px 5px;
}

.header-menu-tag {
  height: 150px;
  padding: 35px 20px 10px;
  border-radius: 10px;
  width: 62%;
  max-height: 120px;
  background-color: grey;
  position: relative;
  margin-top: 63px;
  margin-right: 63px;
  border: black solid;
}

.header-menu-tag .btn-views-all-tag {
  position: absolute;
  left: 88%;
  top: 2%;
  right: 20%;
  width: 100px;
  margin: 5px auto;
  background-color: yellow;
  justify-content: center;
}

.header-menu-card-box {
  background-color: red;
  height: 150px;
  margin-top: 50px;
  margin-left: 20px;
  margin-right: 20px;
  padding: 20px;
  border-radius: 10px 10px 0px 0px;
  width: 30%;
}

.header-menu-card-box .header-text {
  margin: 30px auto;
  background-color: white;
  text-align: center;
}

.menu-card-box {
  background-color: orange;
  margin-left: 20px;
  margin-right: 20px;
  padding: 20px;
  border-radius: 0px 0px 10px 10px;
}

.v-card--reveal {
  align-items: center;
  bottom: 0;
  justify-content: center;
  opacity: 0.5;
  position: absolute;
  width: 100%;
}
</style>


