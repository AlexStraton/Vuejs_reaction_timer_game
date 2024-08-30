<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click me</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showBlock: false,
      timer: null,
      reactionTime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.reactionTime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("endGame", this.reactionTime);
    },
  },
};
</script>

<style>
.block {
  position: absolute;
  top: 60%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: rgb(17, 195, 183);
  height: 15rem;
  width: 25rem;
  border-radius: 30px;
  font-size: 3rem;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
