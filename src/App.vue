<template>
  <div id="header">
    <router-link to="/">Home</router-link> |
    <router-link to="/Search">Rechercher</router-link> |
  </div>
  <router-view />
  <div id="footer">
    <p>&copy;teamChampions</p>
  </div>
  
</template>

<script>
 
 
export default {
  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
