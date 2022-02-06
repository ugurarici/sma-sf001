<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/profile">Profile</router-link> |
      <router-link to="/counter">Counter</router-link>
    </div>
    <div style="margin-bottom: 30px">
      <router-link
        v-for="pokemon in pokemons.results"
        :key="pokemon.name"
        :to="'/pokemon/' + pokemon.name"
        style="padding: 5px"
      >
        {{ pokemon.name }}
      </router-link>
    </div>
    <router-view />
  </div>
</template>

<script>
export default {
  data() {
    return {
      pokemons: [],
    };
  },
  beforeMount() {
    fetch("https://pokeapi.co/api/v2/pokemon?limit=10&offset=20")
      .then((response) => response.json())
      .then((data) => (this.pokemons = data));
  },
};
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
