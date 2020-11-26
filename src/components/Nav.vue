
<template>
  <div>
    <div class="header-nav">


        <!-- Nav Icon src="../assets/cover_khaokrua.jpg"-->

        <!-- Logo KhaoKrua -->

        <h1>KhaoKrua</h1>
        <!-- <div class="header-nav-logo">
          <div class="nav-logo" style="background-color: black;">
            <v-img
              alt="khaokrua Logo"
              class="shrink mr-2"
              contain
              src="../assets/KhaoKrua_logo.png"
              transition="scale-transition"
              width="360px"
              style="background-color: red"
            />
          </div>
        </div> -->

        <ul>
          <li><a href="">Add</a></li>
          <li><a href="">Fav</a></li>
          <li><a href="">Profile</a></li>
          <li><a href="">Profile</a></li>
          <li><a href="">Profile</a></li>
          <li><a href="">Profile</a></li>
        </ul>

      </div>
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

*{
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.header-nav{
  width: 100%;
  height: 360px;
  padding: 60px 0;
  background-color: white;
  border-bottom: #e1e1e1;
  top: 0;
  display: flex;
  justify-content: space-between;
  transition: all 0.4s ease-in-out;
  z-index: 9999;
  position: fixed;
}
/* 
.nav-logo{
  width: 50%;
} */

.header-nav h1 {
  font-size: 85px;
  text-indent: 40px;
  font-weight: bold;
  float: left;
  margin-left: 10%;
  margin-top: 0;
}

ul {
  margin-top: 3%;
  margin-right: 0;
  float: right;
  padding: 0px;
  width: 30%;
}

li{
  display: inline-block;
  margin-top: 0%;
  margin-right: 3%;
}

a{
  text-decoration: none;
  color: black;
}

.shink {
  padding: 20px 0;
}

.header-nav .search-field {
  display: flex;
  position: absolute;
  top: 100%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: rgb(0, 0, 0, 0.1);
  max-width: 1000px;
  height: 80px;
  width: 47.5%;
  padding: 15px;
  justify-content: space-between;
  border-radius: 8px;
}

.header-nav-icon .nav-nav-icon {
  margin: 8px;
}



.header-nav-menu {
  height: 80px;
  position: relative;
}
.header-nav-menu .nav-menu {
  margin: 0px 90px 0px;
  width: 80%;
  display: flex;
  justify-content: space-between;
  padding: 5px 5px 5px;
}

.btn-add-recipe v-btn > span {
  vertical-align: middle;
}

.header-nav-menu .nav-menu .btn-add-recipe {
  /* background-color: blue; */
  height: 15%;
}

.header-nav-menu .nav-menu .btn-fav-recipe {
  /* background-color: blue; */
  height: 15%;
}

.header-nav-menu .nav-menu .btn-profile {
  margin: 0;
  /* background-color: black; */
}
</style>