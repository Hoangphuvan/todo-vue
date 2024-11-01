<script>
import { nanoid } from "nanoid";
import ToDoItem from "./components/ToDoItem.vue";
import ToDoForm from "./components/ToDoForm.vue";

export default {
  name: "app",
  components: {
    ToDoItem,
    ToDoForm,
  },
  data() {
    return {
      ToDoItems: [
        { id: "todo-" + nanoid(), label: "Learn Vue", done: false },
        {
          id: "todo-" + nanoid(),
          label: "Create a Vue project with the CLI",
          done: true,
        },
        { id: "todo-" + nanoid(), label: "Have fun", done: true },
        {
          id: "todo-" + nanoid(),
          label: "Create a to-do list",
          done: false,
        },
      ],
    };
  },
  methods: {
    addToDo(toDoLabel) {
      this.ToDoItems.push({
        id: "todo-" + nanoid(),
        label: toDoLabel,
        done: false,
      });
    },
  },
};
</script>

<template>
  <div id="app">
    <h1>To-Do List</h1>
    <to-do-form @todo-added="addToDo"></to-do-form>
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
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
