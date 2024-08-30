<template>
  <h1>Reaction Timer</h1>
  <h2>This game tests your reaction time!</h2>
  <p>Click play. Click on the green block...if you can 👀</p>
  <Block v-if="isCurrentlyPlaying" :delay="delay" @endGame="endGame" />
  <ResultsModal
    :score="score"
    :showResults="showResults"
    :showModal="showModal"
    @close="handleModalClose" />

  <button
    @click="start"
    :disabled="isCurrentlyPlaying"
    :style="{ backgroundColor: isCurrentlyPlaying ? 'grey' : 'purple' }">
    Play
  </button>
</template>

<script>
import Block from "./components/Block.vue";
import ResultsModal from "./components/Results.vue";

export default {
  name: "App",
  components: { Block, ResultsModal },
  props: ["reactionTime"],
  data() {
    return {
      isCurrentlyPlaying: false,
      delay: null,
      score: null,
      showResults: false,
      showModal: false,
    };
  },
  methods: {
    start() {
      this.isCurrentlyPlaying = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showResults = false;
      this.showModal = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isCurrentlyPlaying = false;
      this.showResults = true;
      this.showModal = true;
    },
    handleModalClose() {
      this.showModal = false;
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
