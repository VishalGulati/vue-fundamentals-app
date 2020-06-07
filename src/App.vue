<template>
  <v-app>
    <div id="app">
      <AppHeader />
      <div class="app-body">
        <router-view />
      </div>
      <AppFooter />
    </div>
    <Loader />
  </v-app>
</template>

<script>
import AppHeader from "@/components/AppHeader/AppHeader.vue";
import AppFooter from "@/components/AppFooter/AppFooter.vue";
import Loader from "@/shared/Loader.vue";

export default {
  name: "app",
  components: {
    AppHeader,
    AppFooter,
    Loader
  }
};
</script>

<style>
body {
  font-size: 16px;
  margin: 0;
  background: #ece9e6;
}

.application--wrap {
  display: block !important;
}

.theme--light.application {
  background: inherit;
}

#app {
  font-family: monospace, sans-serif, "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0 auto !important;
}

.app-body {
  margin-top: 80px;
}
</style>
