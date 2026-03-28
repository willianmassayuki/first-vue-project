<template>
  <div class="box">
    {{ text }}
    <span :class="['status', status]">{{ status }}</span>
  </div>
</template>

<script>
export default {
  name: "MyBox",

  props: {
    text: {
      type: String,
      default: "N/A",
    },

    status: {
      type: String,
      validator: (value) => ["active", "inactive"].includes(value),
      default: "active",
    },
  },
};
</script>

<style>
.box {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 4px;
  width: 30px;
  min-width: fit-content;
  height: 30px;
  padding: 4px 8px;
  background-color: aquamarine;
}

.active {
  background-color: green;
}

.inactive {
  background-color: red;
}
</style>
