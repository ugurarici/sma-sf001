<template>
  <div>
    {{ count }}
    <button @click="increment">++</button>
    <button @click="decrement">--</button>
    <hr />
    <input type="number" v-model="newCountValue" />
    <button @click="setCountTo(newCountValue)">Set</button>
  </div>
</template>

<script>
import { mapMutations } from "vuex";

export default {
  data() {
    return {
      newCountValue: null,
    };
  },
  computed: {
    count() {
      return this.$store.state.count;
    },
  },
  methods: {
    // increment() {
    //   this.$store.commit("increment");
    // },
    ...mapMutations(["increment", "decrement", "setCountTo"]),
  },
};
</script>