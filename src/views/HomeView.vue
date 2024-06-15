<template>
  <div class="nav-bar"><img alt="Vue logo" src="../assets/logo.png" /></div>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
.nav-bar {
  background: linear-gradient(-90deg, #e94817, #d1e704);
  height: 60px;
  margin-bottom: 25px;
  -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.57);
  text-align: center;
  font-size: larger;
  font-family: "Lucida Sans", "Lucida Sans Regular";
  font-style: oblique;
}
</style>