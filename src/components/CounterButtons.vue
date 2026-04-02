<template>
  <div class="buttons">
    <h3>Valor atual de Count: {{ countValue }}</h3>
    <MyButton
      :disabled="!canDecrement"
      @update="$emit('change-count', 'decrement', 1)"
      title="-1"
    />
    <MyButton @update="$emit('change-count', 'increment', 1)" title="+1" />
    <MyButton
      :disabled="!canReset"
      @update="$emit('change-count', 'reset')"
      title="Resetar"
    />
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
  props: {
    countValue: {
      type: Number,
      required: true,
    },
  },

  computed: {
    canDecrement() {
      return this.countValue > -10;
    },
    canReset() {
      return this.countValue !== 0;
    },
  },
};
</script>

<style>
.buttons {
  display: flex;
  gap: 10px;

  button:disabled {
    cursor: default;
    opacity: 0.5;
  }
}
</style>
