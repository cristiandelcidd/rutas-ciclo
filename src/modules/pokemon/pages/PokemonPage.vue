<template>
  <h1>
    Pokemon #<span> {{ id }}</span>
    <div v-if="pokemon">
      <img :src="pokemon.sprites.front_default" :alt="pokemon.name" />
      <p>{{ pokemon.name }}</p>
    </div>
  </h1>
</template>

<script>
export default {
  props: {
    id: { type: Number, required: true },
  },
  data() {
    return {
      pokemon: null,
    };
  },
  created() {
    // console.log(this.$route);
    // const { id } = this.$route.params;
    // console.log(id);
    // this.id = id;
    this.getPokemon();
  },
  methods: {
    async getPokemon() {
      this.pokemon = null;
      try {
        const pokemon = await fetch(
          `https://pokeapi.co/api/v2/pokemon/${this.id}`
        );

        this.pokemon = await pokemon.json();

        // console.log(this.pokemon);
      } catch (error) {
        this.$router.push("/");
      }
    },
  },
  watch: {
    id() {
      this.getPokemon();
    },
  },
};
</script>

<style scoped>
img {
  width: 300px;
  height: 300px;
}

p {
  text-align: center;
}
</style>
