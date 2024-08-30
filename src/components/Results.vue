<template>
  <div v-if="showModal" @click.self="closeModal" class="backdrop">
    <div class="modal">
      <p v-if="showResults">Reaction Time: {{ score / 1000 }} seconds</p>
      <p>😊</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["showResults", "score", "showModal"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  height: 400px;
  font-size: xx-large;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
  z-index: 6;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
  z-index: 5;
}
</style>
