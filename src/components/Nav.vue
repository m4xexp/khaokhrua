<template>
  <nav>
    <v-toolbar
      app
      dark
      prominent
      extended
      src="../assets/cover_khaokrua.jpg"
      height="280px"
      elevate-on-scroll
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      <!-- Spacing for Logo -->
      <v-spacer></v-spacer>
      <v-spacer></v-spacer>

      <div class="d-flex align-center">
        <a href="">
          <v-img
            alt="khaokrua Logo"
            class="shrink mr-2"
            contain
            src="../assets/KhaoKrua_logo.png"
            transition="scale-transition"
            width="360"
          />
        </a>
      </div>
      <v-spacer></v-spacer>
      <!-- Button for Nav -->
      <v-btn left text>
        <v-icon>add</v-icon>
        <span>เพิ่มสูตรอาหาร</span>
      </v-btn>

      <v-btn left text>
        <v-icon left>favorite</v-icon>
        <span>เมนูโปรด</span>
      </v-btn>
      <div class="text-center">
        <v-menu bottom min-width="200px" rounded offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn icon x-large v-bind="attrs" v-on="on">
              <v-avatar>
                <img src="../assets/Profile/miew.jpg" alt="miew" />
              </v-avatar>
            </v-btn>
          </template>
          <v-card>
            <v-list-item-content class="justify-center">
              <div class="mx-auto text-center">
                <v-btn x-large icon>
                  <v-avatar>
                    <img src="../assets/Profile/miew.jpg" alt="nong" />
                  </v-avatar>
                </v-btn>
                <h4>{{ user.fullName }}</h4>
                <p class="caption mt-1">
                  {{ user.email }}
                </p>
                <v-divider class="my-3"></v-divider>

                <v-btn depressed rounded text href="#">
                  <v-icon left>account_circle</v-icon>แก้ไขโปรไฟล์
                </v-btn>
                <v-divider class="my-3"></v-divider>
                <v-btn depressed rounded text href="#">
                  <v-icon left>add</v-icon> เพิ่มสูตรอาหาร
                </v-btn>
                <v-divider class="my-3"></v-divider>
                <v-btn depressed rounded text href="#">
                  <v-icon left>login</v-icon> ออกจากระบบ
                </v-btn>
              </div>
            </v-list-item-content>
          </v-card>
        </v-menu>
      </div>
    </v-toolbar>
    
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
  </nav>
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

<style>
</style>