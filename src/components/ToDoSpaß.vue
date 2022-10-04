<!-- Create a toDoList with vue -->

<template>

    <h1>
        To Do List
    </h1>
    <div>
      <input type="text" v-model="newToDo" @keyup.enter="addToDo()" />
      <button @click="addToDo()">Add</button>
      <ul>
        <li v-for="(todo, index) in todos" :key="index">
          {{ todo }}
          <button @click="removeToDo()">Remove</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    name: "ToDoListe",
    data() {
      return {
        newToDo: "",
        todos: ["Eat", "Sleep", "Code"],
      };
    },
    methods: {
      addToDo() {
        this.todos.push(this.newToDo);
        this.newToDo = "";
      },
      removeToDo() {
        this.todos.pop();
      },
    },
  };
  </script>