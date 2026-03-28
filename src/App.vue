<template>
  <h1>Basics</h1>
  <h2>Passing props to children components</h2>
  <div class="container-box">
    <MyBox text="1" />
    <MyBox text="2" />
    <MyBox text="3" />
  </div>

  <h2>Getting props from children components</h2>
  <p>{{ count }}</p>

  <CounterButtons @change-count="handleCountChange" />
</template>

<script>
import CounterButtons from "./components/CounterButtons.vue";
import MyBox from "./components/MyBox.vue";

export default {
  name: "App",
  components: {
    MyBox,
    CounterButtons,
  },

  data() {
    return {
      count: 0,
    };
  },

  methods: {
    handleCountChange(action, value = 1) {
      switch (action) {
        case "increment":
          this.count += value;
          break;
        case "decrement":
          this.count -= value;
          break;
        case "reset":
          this.count = 0;
          break;
      }
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
