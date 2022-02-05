<template>
  <span>
    <button @click.prevent="count++">Like ({{ count }})</button>
  </span>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
};
</script>