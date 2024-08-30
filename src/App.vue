<template>
  <h1>Reaction Timer</h1>
  <h2>This game tests your reaction time!</h2>
  <p>Click play and as soon as you see the green block appear, click on it.</p>
  <button @click="start">Play</button>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      isCurrentlyPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.isCurrentlyPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      console.log(this.delay);
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
button {
  background-color: purple;
  width: 140px;
  border-radius: 5px;
  font-weight: bold;
  font-size: 18px;
  font-family: monospace;
  color: white;
  padding: 20px;
  margin-left: 10px;
  text-align: center;
  cursor: pointer;
}
</style>
