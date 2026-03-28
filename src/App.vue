<template>
  <div class="container-box">
    <MyBox text="1" />
    <MyBox text="2" />
    <MyBox text="3" />
  </div>
</template>

<script>
import MyBox from "./components/MyBox.vue";

export default {
  name: "App",
  components: {
    MyBox,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container-box {
  display: flex;
  gap: 8px;
}
</style>
