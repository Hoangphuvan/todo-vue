<script setup>
import ToDoItem from "./components/ToDoItem.vue";
</script>

<template>
  <div id="app">
    <h1>To-Do List</h1>
    <ul>
      <li>
        <to-do-item label="My to-do item" :done="false"></to-do-item>
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
