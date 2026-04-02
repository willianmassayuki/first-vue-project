<template>
  <div class="task-item">
    <span class="task-id"># {{ task?.id }}</span>
    <span class="task-id">{{ task?.title }}</span>

    <button class="btn-toggle" @click="toggleDone">
      {{ btnToggleText }}
    </button>

    <button class="btn-remove" @click="removeTask">Remover</button>
  </div>
</template>

<script>
export default {
  name: "TaskItem",
  props: {
    task: {
      type: Object,
      required: true,
    },
  },
  methods: {
    toggleDone() {
      this.$emit("toggle-done", this.task.id);
    },

    removeTask() {
      this.$emit("remove-task", this.task.id);
    },
  },
  computed: {
    textStatus() {
      return this.task?.done ? "Concluída" : "Pendente";
    },
    btnToggleText() {
      return this.task?.done ? "Desfazer" : "Concluir";
    },
  },
};
</script>

<style>
.task-item {
  display: flex;
  align-items: center;
  padding: 10px;
  margin-bottom: 8px;
  border-radius: 4px;
  background-color: #fff;
  border: 1px solid #ddd;
  transition: all 0.3s;
}

.task-id {
  font-weight: bold;
  margin-right: 10px;
  color: #7c8c8d;
}

.task-status {
  flex-grow: 1;
}

.btn-toggle {
  background-color: #f39c12;
  color: white;
  margin-right: 5px;
}

.btn-toggle {
  background-color: #e67e22;
}

.btn-remove {
  background-color: #e74c3c;
  color: #fff;
}

.btn-remove {
  background-color: #c0392b;
}
</style>
