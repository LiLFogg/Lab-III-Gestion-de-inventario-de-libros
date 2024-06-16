<template>
  <nav class="nav-bar">
    <router-link to="/">Home</router-link> 
    
  </nav>
  <router-view/>
</template>

<style>
#app {
  background: linear-gradient(-90deg, #d0e7047c, #e948176b);
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-right: 15px;
}
.nav-bar {
  background: linear-gradient(-90deg, #e94817, #d1e704);
  width: auto;
  height: 60px;
  margin-bottom: 25px;
  -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.57);
  text-align: center;
  font-size: larger;
  font-style:italic;
}
nav {
  padding: 10px;
  padding-right: 10px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
