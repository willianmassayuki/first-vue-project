<template>
  <div class="task-list-container">
    <h2>Lista de Tarefas</h2>

    <div class="controls">
      <button class="btn-add">Adicionar nova tarefa</button>
      <button class="btn-toggle-all">Marcar todas</button>
      <button class="btn-clear">Limpar concluídas</button>
    </div>

    <div tasks-container>
      <div class="pending-tasks">
        <h3>Tarefas Pendentes</h3>
        <TaskItem />
      </div>

      <div class="completed-tasks">
        <h3>Tarefas Concluídas</h3>
        <TaskItem />
      </div>

      <div>Aqui virá o componente dos contadores</div>
    </div>
  </div>
</template>

<script>
import TaskItem from "./TaskItem.vue";

export default {
  name: "TaskList",
  components: { TaskItem },
};
</script>

<style>
.task-list-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
}

h2 {
  color: #3498db;
  margin-bottom: 20px;
  padding-bottom: 10px;
  border-bottom: 2px solid #f0f0f0;
  text-align: center;
}

.controls {
  display: flex;
  gap: 10px;
  margin-bottom: 30px;
  flex-wrap: wrap;
  justify-content: center;
}

button {
  padding: 10px 20px;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-weight: bold;
  transition: ease 0.3s;
  font-size: 14px;
}

.btn-add {
  background-color: #2ecc71;
  color: white;
}

.btn-add:hover {
  background-color: #27ae60;
  transform: translateY(-2px);
}

.btn-toggle-all {
  background-color: #3498db;
  color: white;
}

.btn-toggle-all:hover {
  background-color: #2980b9;
  transform: translateY(-2px);
}

.btn-clear {
  background-color: #e73c4c;
  color: white;
}

.btn-clear:hover {
  background-color: #c0392b;
  transform: translateY(-2px);
}

.task-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 30px;
  margin-bottom: 30px;
}

.pending-tasks,
.completed-tasks {
  padding: 20px;
  border-radius: 8px;

  h3 {
    margin-top: 0;
    margin-bottom: 15px;
    color: #2c3e50;
    text-align: center;
  }
}

.pending-tasks {
  background-color: #f9f9f9;
  border: 2px solid #eee;
}

.completed-tasks {
  background-color: #f0fff0;
  border: 2px solid #d4edda;
}
</style>
