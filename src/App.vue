<template>
  <Navbar />
  <router-view></router-view>
</template>

<script>
import { defineAsyncComponent } from "vue";

export default {
  name: "App",
  components: {
    Navbar: defineAsyncComponent(() =>
      import(
        /* webpackChunkName: "Navbar" */ "@/modules/shared/components/Navbar"
      )
    ),
  },
};
</script>

<style>
#app {
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  color: #2c3e50;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin-top: 60px;
  text-align: center;
}
</style>
