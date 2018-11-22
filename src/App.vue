<template>
  <div id="app">
    <app-header></app-header>
    <app-user @name="calLove" style="margin-top: 30px;"> </app-user>
  </div>
</template>

<script>
import myHeader from "./components/myHeader.vue";
import user from "./components/users.vue";

export default {
  name: "App",
  components: {
    appUser: user,
    appHeader: myHeader
  },
  methods: {
    calLove(user1, user2) {
      var love = 0;
      let user = user1 + user2;
      for (let i = 0; i < user.length; i++) {
        love = love + user.charCodeAt(i);
      }
      alert((love % 100) + "% Loves in air!");
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
