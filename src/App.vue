<template>
  <div id="app">
    <div id="nav">
      <div class="logo"><h1><span>SKKU</span>졸업관리시스템</h1></div>
      <div class="menu">
        <div class="menu_item" v-for="item in menus" v-bind:key="item.name">
          <router-link :to="{ path: item.url }">{{ item.name }}</router-link>
        </div>
      </div>
    </div>
    <router-view/>
  </div>
</template>

<script>
import Menu from './models/menu/Menu.js'

const menus = [
    new Menu('졸업요건', '/graduation_rule'),
    new Menu('졸업관리', '/graduation_management'),
    new Menu('학교홈페이지', '/school_homepage'),
    new Menu('종합정보시스템', '/jonghab'),
    new Menu('로그인', '/login')
];

export default {
  components: {
      Menu
  },
  data() {
      return {
          menus
      }
  }
}
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 40px;
}

span {
  color: #1BBD36;
}

h1 {
  margin: 0;
  padding: 0;
  float: left;
  font-size: 25px;
  color: #333;
  text-transform: uppercase;
  font-weight: 900;
}

a {
  text-decoration: none;
}

.logo {
  margin: 0 0 0 5%;
}

.menu {
  display: flex;
  justify-content: space-between;
  margin: 0 5% 0 40%;
}

.menu_item a{
  color: #333;
  font-weight: 700;
}

</style>
