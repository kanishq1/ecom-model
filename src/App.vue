<template>
  <div>
    <div id="app">
      <Header />
      <div id="nav">
        <router-link to="/">Home</router-link>|
        <router-link to="/about">About</router-link>|
        <router-link to="/cart">Cart</router-link>
      </div>
    </div>
    <router-view />
  </div>
</template>
<script>
import Header from "./components/layout/Header";
export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style scoped>
body {
  background-color: rgb(199, 197, 194);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding-top: 100px;
  font-size: 1.6rem;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #b942af;
}
</style>
