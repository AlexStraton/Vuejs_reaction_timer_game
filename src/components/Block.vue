<template>
  <div class="block">Click me</div>
</template>

<script>
export default {
  props: ["delay"],
};
</script>

<style>
.block {
  position: absolute;
  top: 50%;
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
