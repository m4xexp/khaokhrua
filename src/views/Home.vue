<template>
  <div class="home-container">
    <!-- Header above card box -->

    <div class="flex-header">
      <!-- Suggest topic -->

      <div class="header-menu-card-box">
        <div class="header-text">
          <h1 class="text-menu-suggest" style="vertical-align: middle">
            เมนูเเนะนำสำหรับคุณ
          </h1>
        </div>
      </div>

      <!-- Tag box -->

      <div class="header-menu-tag" style="display: flex">
        <div class="btn-views-all-tag" style="display: flex">
          <h5>ดูทั้งหมด</h5>
          <v-icon>arrow_right_alt</v-icon>
        </div>

        <div class="menu-tag-box">
          <div class="menu-tag-cover" v-for="tag in tags" :key="tag.tagName">
            <v-chip
              link
              outlined
              class="ma-3"
              color="black"
              label
              text-color="black"
              large
            >
              {{ tag.tagName }}
            </v-chip>
          </div>
        </div>
      </div>
    </div>

    <!-- Card menu -->

    <div class="menu-card-box">
      <v-layout row wrap class="menu-card-cober-each-card">
        <v-flex
          xs12
          sm6
          md4
          lg3
          v-for="recipe in menus"
          :key="recipe.Name"
          class="menu-card-each-card"
        >
          <!-- Card -->

          <v-card
            :loading="loading"
            class="mx-auto"
            max-width="374"
            id="card-recipe"
          >
            <template slot="progress">
              <v-progress-linear
                color="deep-purple"
                height="10"
                indeterminate
              ></v-progress-linear>
            </template>

            <!-- Img for recipe card -->

            <v-img
              class="card-recipe-img"
              height="250"
              src= "../assets/Recipe/beefwell.jpg"
            ></v-img>

            <div class="btn-fav-recipe">
              <div>
                <v-icon class="btn-fav-recipe-icon" style=""
                  >favorite_border</v-icon
                >
              </div>
            </div>

            <v-card-title style="font-size: 28px">{{
              recipe.Name
            }}</v-card-title>

            <v-card-text class="card-data">
              <div class="box-card-data">
                <div class="card-data-cook-time">
                  <v-icon left>schedule</v-icon>
                  <span style="vertical-align: middle"
                    >{{ recipe.time }} ชั่วโมง</span
                  >
                </div>
                <div class="card-data-cook-time" style="margin-left: 15px">
                  <v-icon left>group</v-icon>
                  <span style="vertical-align: middle">สำหรับ 2 ที่</span>
                </div>
              </div>

              <v-row align="center" class="mx-0">
                <v-rating
                  :value="recipe.rate"
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
              <v-btn
                block
                dark
                text
                @click="reserve"
                style="background-color: green"
              >
                <span>ทำอาหาร</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </div>

    <!-- Button All recipe -->

    <div class="wraper-btn-see-all-recipe">
      <v-btn large color="success" class="btn-see-all-recipe">
        <span class="all-recipe-text">สูตรอื่นๆ</span>
      </v-btn>
    </div>
    <div>
      <Pagination />
  </div>
  </div>
</template>

<script>
import Pagination from "./Pagination.vue";
// import Searchrecipe from "./SearchRecipe.vue";

export default {
  name: "Home",

  components: {
    Pagination,
    // SearchRecipe,
  },

  pagination () {
      return {
        page: 1,
      }
    },

  data: () => ({
    menus: [
      { Name: "Beef Welling Ton", Author: "KhaoKrua", time: "2", rate: "1",src: "../assets/Recipe/beefwell.jpg"},
      { Name: "Tomyum Kung", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "ข้าวผัดหมูสับ", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Tomyum Kung", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Beef Welling Ton", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
      { Name: "Tomyum Kung", Author: "KhaoKrua", time: "1", rate: "4.7",src: "../assets/Recipe/beefwell.jpg" },
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

.menu-tag-box {
  margin-top: 10px;
  margin-right: 20px;
  height: 50px;
  display: flex;
  position: absolute;
}
.home-container {
  width: 90%;
  margin-left: 5rem;
  position: relative;
}

.home-container .wraper-btn-see-all-recipe {
  height: 100px;
  padding: 50px;
  background-color: white;
  position: relative;
  margin-left: 20px;
  margin-right: 20px;
}

.wraper-btn-see-all-recipe .btn-see-all-recipe {
  position: absolute;
  left: 50%;
  right: 50%;
  transform: translate(-50%, -50%);
  width: 200px;
}

.flex-header {
  display: flex;
  justify-content: space-between;
}

.menu-card-cober-each-card .menu-card-each-card {
  padding: 5px 5px 5px 5px;
}

.menu-card-each-card .btn-fav-recipe .btn-fav-recipe-icon {
  position: absolute;
  left: 80%;
  bottom: 38%;
  background: red;
  color: white;
  font-size: 1.2em;
  font-weight: bold;
  padding: 15px;
  border-radius: 50%;
}

.menu-card-each-card
  .btn-fav-recipe:hover
  + .menu-card-each-card
  .btn-fav-recipe {
  display: block;
}

.header-menu-tag {
  height: 150px;
  padding: 35px 20px 10px;
  border-radius: 10px;
  width: 62%;
  max-height: 120px;
  background-color: white;
  position: relative;
  margin-top: 63px;
  margin-right: 63px;
}

.header-menu-tag .btn-views-all-tag {
  position: absolute;
  left: 88%;
  top: 2%;
  right: 20%;
  width: 100px;
  margin: 5px auto;
  justify-content: center;
}

.header-menu-card-box {
  background-color: white;
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

#card-recipe .card-recipe-img {
  background-size: 150%;
}

.menu-card-box {
  background-color: white;
  margin-left: 20px;
  margin-right: 20px;
  padding: 20px;
}

.card-data .box-card-data {
  display: flex;
  justify-content: flex-start;
  margin: 10px auto;
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


