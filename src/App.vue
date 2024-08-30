<template>
  <h1>Reaction Timer</h1>
  <button @click="start">Play</button>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      title: "my first Vue App",
    };
  },
  methods: {
    start() {
      isCurrentlyPlaying = true;
      setTimout(() => {
        console.log("timer");
      }, 4000);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
</style>
