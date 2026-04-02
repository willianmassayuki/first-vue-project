<template>
  <TaskList />
</template>

<script>
import TaskList from "./components/TaskList.vue";

export default {
  name: "App",
  components: {
    TaskList,
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
      console.log("count newValue", newValue);
      console.log("count oldValue", oldValue);
      localStorage.setItem("count", newValue);
    },
    changeColorCount(newValue) {
      console.log("changeColorCount newValue", newValue);
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
