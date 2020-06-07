<template>
  <header>
    <router-link class="nav-link" to="/">Vue.JS Sample App</router-link>
    <router-link class="nav-link charts-link" to="/posts">Posts</router-link>
  </header>
</template>

<script>
export default {
  name: "AppHeader"
};
</script>

<style>
header {
  background-color: #1cd8d2;
  color: azure;
  text-align: left;
  font-size: 1.5rem;
  padding: 20px;
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 2;
}

.nav-link {
  text-decoration: none;
  color: inherit;
}

.charts-link {
  float: right;
  color: orangered;
}
</style>
