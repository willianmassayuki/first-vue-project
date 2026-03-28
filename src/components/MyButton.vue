<template>
  <button @click="$emit('update')">{{ title }}</button>
</template>

<script>
export default {
  name: "MyButton",

  props: {
    title: {
      type: String,
      default: "+1",
    },
  },
};
</script>

<style>
button {
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-family: inherit;
  background-color: blueviolet;
}
</style>
