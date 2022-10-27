<template>
  <nav>
    <router-link to="/">Pokemon List</router-link>
    <router-link to="/id">Pokemon by id</router-link>
    <router-link to="/about">About</router-link>
  </nav>
</template>

<style scoped>
nav {
  display: flex;
  justify-content: center;
  gap: 1rem;
}

a,
a:active {
  color: #000;
  text-decoration: none;
}

.router-link-exact-active {
  color: #42b983;
  text-decoration: underline;
}
</style>
