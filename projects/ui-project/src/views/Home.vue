<template>
  <div class="home">
    <template v-if="pokemon">
      <img
        v-if="pokemon.sprites.front_default"
        alt="Vue logo"
        :src="pokemon.sprites.front_default"
      />
      <p v-if="pokemon.name">{{ pokemon.name }}</p>
    </template>

    <img v-else alt="Vue logo" src="../assets/logo.png" />

    <hr />
    Count: {{ count }}
    <hr />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  data() {
    return {
      pokemon: null,
    };
  },
  components: {
    HelloWorld,
  },
  computed: {
    count() {
      return this.$store.state.count;
    },
  },
  beforeMount() {
    fetch("https://pokeapi.co/api/v2/pokemon/pikachu")
      .then((response) => response.json())
      .then((data) => {
        this.pokemon = data;
      });
  },
};
</script>
