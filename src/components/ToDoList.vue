<script setup>
    import {ref} from "vue"

    const list = ref([]);
    const input = ref("");

    function add() {
        list.value.push(input.value);
        input.value = "";
    }

    function remove(index) {
        list.value.splice(index, 1);
    }
</script>


<template>

    
    <div>
        <h1>
            To Do List
        </h1> 

        <input v-model="input" @keyup.enter="add()"/>&nbsp &nbsp
        <button @click="add">
            Add
        </button>
        
    <ul>
        <li v-for="item in list" :key="item">
            {{item}} &nbsp &nbsp
            <button @click="remove"> X </button>
        </li>
    </ul>
    </div>
  </template>




