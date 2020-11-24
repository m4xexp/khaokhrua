
<template>
  <div>
    <v-app-bar
      class="header-nav"
      dark
      app
      src="../assets/cover_khaokrua.jpg"
      height="280px"
    >
      <div class="sub-header-nav">
        <div class="header-nav-icon">
          <div class="nav-nav-icon">
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
          </div>
        </div>
        <div class="header-nav-logo">
          <div class="nav-logo">
            <v-img
              alt="khaokrua Logo"
              class="shrink mr-2"
              contain
              src="../assets/KhaoKrua_logo.png"
              transition="scale-transition"
              width="360"
            />
          </div>
        </div>

        <!-- Seach Receipt -->

        <div class="search-field">
          <div class="search-text-field-bar">
            <v-text-field
              light
              style="width: 600px"
              value="Beef Wellington"
              label="ทำอะไรกินดีน้า"
              solo
            ></v-text-field>
          </div>
          <div class="btn-search-icon">
            <v-btn large color="red darken-1">
              <v-icon large color="white" alt="searchRecipt">search</v-icon>
            </v-btn>
          </div>
        </div>

        <!-- Nav menu -->

        <div class="header-nav-menu">
          <div class="nav-menu">
            <div class="btn-add-receipt">
              <v-btn left text>
                <v-icon style="margin-top: 2px">add</v-icon>
                <span>เพิ่มสูตรอาหาร</span>
              </v-btn>
            </div>
            <div class="btn-fav-receipt">
              <v-btn left text>
                <v-icon left style="margin-top: 6px">favorite</v-icon>
                <span>เมนูโปรด</span>
              </v-btn>
            </div>

            <!-- Profile Menu -->

            <div class="btn-profile">
              <v-menu bottom min-width="200px" rounded offset-y>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn icon x-large v-bind="attrs" v-on="on">
                    <v-avatar>
                      <img src="../assets/Profile/miew.jpg" alt="miew" />
                    </v-avatar>
                  </v-btn>
                </template>
                <v-card>
                  <v-list-item-content>
                    <div class="mx-auto text-center">
                      <!-- Profile button -->
                      <v-btn x-large icon>
                        <v-avatar>
                          <img src="../assets/Profile/miew.jpg" alt="nong" />
                        </v-avatar>
                      </v-btn>
                      <div class="prfile-title" style="margin: 10px">
                        <h4 class="profile-title-name">{{ user.fullName }}</h4>
                        <p class="caption mt-1" id="profile-title-email">
                          {{ user.email }}
                        </p>
                      </div>
                      <v-divider class="my-3"></v-divider>

                      <v-btn depressed rounded text href="#">
                        <v-icon left style="margin-top: 4px"
                          >account_circle</v-icon
                        >
                        <span>แก้ไขโปรไฟล์</span>
                      </v-btn>

                      <v-divider class="my-3"></v-divider>

                      <v-btn depressed rounded text href="#">
                        <v-icon left style="margin-top: 2px">add</v-icon>
                        <span>เพิ่มสูตรอาหาร</span>
                      </v-btn>

                      <v-divider class="my-3"></v-divider>

                      <v-btn depressed rounded text href="#">
                        <v-icon left style="margin-top: 2px">login</v-icon>
                        <span>ออกจากระบบ</span>
                      </v-btn>
                    </div>
                  </v-list-item-content>
                </v-card>
              </v-menu>
            </div>
          </div>
        </div>
      </div>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute app temporary>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="title"> Application </v-list-item-title>
          <v-list-item-subtitle> subtext </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item v-for="item in items" :key="item.title" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data: () => ({
    image: [{ logoPath: "" }],
    drawer: false,
    items: [
      { icon: "dashboard", title: "แดชบอร์ด", route: "/dashboard" },
      { icon: "folder", title: "โปรเจค", route: "/project" },
    ],
    user: {
      initials: "ploylada",
      fullName: "Ploylada",
      email: "priewmx1027@gmail.com",
    },
  }),
};
</script>

<style scrope>
.header-nav .sub-header-nav {
  display: grid;
  grid-template-columns: 30% 40% 30%;
  width: 100vw;
  height: 280px;
}

.header-nav .search-field {
  display: flex;
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: rgb(0, 0, 0, 0.2);
  max-width: 1000px;
  max-height: 200px;
  height: 27%;
  width: 47.5%;
  padding: 15px;
  justify-content: space-between;
  border-radius: 5px;
}

/* .header-nav .search-field .search-text-field-bar{
  width: 80%;
} */

.header-nav-icon .nav-nav-icon {
  margin: 8px;
}

.header-nav-logo {
  display: flex;
  justify-content: center;
}

.header-nav-logo .nav-logo {
  margin: 50px;
}

.header-nav-menu .nav-menu {
  margin: 0 auto;
  width: 100%;
  display: flex;
  justify-content: flex-end;
  padding: 10px;
}

.header-nav-menu .nav-menu .btn-add-receipt {
  height: 15%;
  margin: 8px 5px;
}

.header-nav-menu .nav-menu .btn-fav-receipt {
  height: 15%;
  margin: 8px 8px;
}
</style>