<template>
  <div id="app">
    <Navbar />
    <router-view />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: {
    Navbar
  }
}

</script>


<style>
@import url("https://fonts.googleapis.com/css?family=Roboto+Condensed");

html,
body {
  font-family: "Roboto", sans-serif;
}

* {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
}

#app {
  font-family: "Roboto", sans-serif;
}

</style>
