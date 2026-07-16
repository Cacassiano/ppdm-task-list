<script setup lang="ts">
import { ref } from "vue";
import TaskList from "./components/TaskList.vue";
const taskList = ref(["Tarefas importantes"]);
const title = ref("");
const handleSubmit = (e: any) => {
  e.preventDefault();
  taskList.value.push(title.value);
  title.value = "";
};
</script>

<template>
  <form @submit="handleSubmit">
    <input
      v-model="title"
      placeholder="crie uma nova lista de Tarefas"
      required
    />
    <button>Create New list</button>
  </form>
  <br />
  <ul v-for="title in taskList">
    <TaskList :title="title" />
  </ul>
</template>
