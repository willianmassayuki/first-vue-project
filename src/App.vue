<template>
  <h1>Basics</h1>
  <h2>Passing props to children components</h2>
  <div class="container-box">
    <MyBox text="1" />
    <MyBox text="2" />
    <MyBox text="3" />
  </div>

  <h2>Learning how to use computed</h2>
  <p :style="{ color: changeColorCount }">{{ count }}</p>

  <CounterButtons @change-count="handleCountChange" :count-value="count" />
  <p :style="{ color: changeColorCount }">{{ countState }}</p>
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
      count: Number(localStorage.getItem("count")) || 0,
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

  computed: {
    changeColorCount() {
      if (this.count === 0) {
        return "black";
      } else if (this.count > 0) {
        return "green";
      }

      return "red";
    },
    countState() {
      if (this.count === 0) return "É zero";
      if (this.count < 0) return "É negativo";
      return "É positivo";
    },
  },

  watch: {
    count(newValue, oldValue) {
      console.log("newValue", newValue);
      console.log("oldValue", oldValue);
      localStorage.setItem("count", newValue);
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
