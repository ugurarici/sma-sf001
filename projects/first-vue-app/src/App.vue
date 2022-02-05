<template>
  <div>
    <p>Merhaba burası App.vue</p>
    <profile :name="name" />
  </div>
</template>

<script>
import Profile from "./components/Profile.vue";

export default {
  name: "App",
  components: {
    Profile,
  },
  data() {
    return {
      name: "Uğur",
    };
  },
};
</script>