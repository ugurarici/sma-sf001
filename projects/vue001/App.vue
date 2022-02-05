<template>
  <div>
    <p>Merhaba burası App.vue</p>
    <profile :name="name" />
  </div>
</template>

<script>
import Profile from "./Profile.vue";

export default {
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