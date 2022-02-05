<template>
  <div>
    Here is the profile of {{ name }}
    <like-button />
  </div>
</template>

<script>
import LikeButton from "./Partials/LikeButton.vue";

export default {
  props: ["name"],
  components: {
    LikeButton,
  },
};
</script>