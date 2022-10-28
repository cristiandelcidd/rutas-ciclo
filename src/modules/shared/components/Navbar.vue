<template>
  <nav>
    <!-- <router-link :to="{ name: 'home' }">Pokemon List</router-link>
    <router-link :to="{ name: 'pokemon-id', params: { id: 100 } }"
      >Pokemon by id</router-link
    >
    <router-link :to="{ name: 'about' }">About</router-link> -->
    <!-- <router-link to="/about">About</router-link> -->
    <CustomLink v-for="link in links" :key="link.to" :link="link" />
  </nav>
</template>

<script>
import { defineAsyncComponent } from "vue";

export default {
  data() {
    return {
      links: [
        { to: "/home", name: "Pokemons" },
        { to: "/pokemonid/50", name: "Pokemon by id" },
        { to: "/about", name: "About" },
        { to: "https://www.google.com/", name: "Google" },
      ],
    };
  },
  components: {
    CustomLink: defineAsyncComponent(() => import("./CustomLink.vue")),
  },
};
</script>

<style scoped>
nav {
  display: flex;
  justify-content: center;
  gap: 1rem;
}
</style>
