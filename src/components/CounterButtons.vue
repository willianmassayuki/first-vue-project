<template>
  <div class="buttons">
    <MyButton @update="$emit('change-count', 'decrement', 1)" title="-1" />
    <MyButton @update="$emit('change-count', 'increment', 1)" title="+1" />
    <MyButton @update="$emit('change-count', 'reset')" title="Resetar" />
  </div>
</template>

<script>
import MyButton from "./MyButton.vue";

export default {
  name: "CounterButtons",
  emits: ["change-count"],
  components: {
    MyButton,
  },
};
</script>

<style>
.buttons {
  display: flex;
  gap: 10px;
}
</style>
