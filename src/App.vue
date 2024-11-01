<script setup>
import { nanoid } from "nanoid";
import ToDoItem from "./components/ToDoItem.vue";

const data = {
  ToDoItems: [
    { label: "Learn Vue", done: false, id: "todo-" + nanoid() },
    {
      label: "Create a Vue project with the CLI",
      done: true,
      id: "todo-" + nanoid(),
    },
    { label: "Create a to-do list", done: false, id: "todo-" + nanoid() },
  ],
};
</script>

<template>
  <div id="app">
    <h1>To-Do List</h1>
    <ul>
      <li v-for="item in data.ToDoItems" :key="item.id">
        <to-do-item
          :label="item.label"
          :done="item.done"
          :id="item.id"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
