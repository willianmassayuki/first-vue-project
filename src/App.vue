<template>
  <h1>Basics</h1>
  <h2>Passing props to children components</h2>
  <div class="container-box">
    <MyBox text="1" />
    <MyBox text="2" />
    <MyBox text="3" />
  </div>

  <h2>Getting props from children components</h2>
  <div>
    <p>{{ count }}</p>
    <MyButton @update="decrementCount" title="-1" />
    <MyButton @update="incrementCount" title="+1" />
    <MyButton @update="clear" title="Zerar" />
  </div>
</template>

<script>
import MyBox from "./components/MyBox.vue";
import MyButton from "./components/MyButton.vue";

export default {
  name: "App",
  components: {
    MyBox,
    MyButton,
  },

  data() {
    return {
      count: 0,
    };
  },

  methods: {
    incrementCount() {
      this.count++;
    },
    decrementCount() {
      this.count--;
    },
    clear() {
      this.count = 0;
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
  color: #2c3e50;
  margin-top: 60px;
}

.container-box {
  display: flex;
  gap: 8px;
}
</style>
