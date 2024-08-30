<template>
  <p v-if="showResults">Reaction Time: {{ score / 1000 }} seconds</p>
</template>

<script>
export default {
  props: {
    score: Number,
    showResults: Boolean,
  },
};
</script>

<style></style>
