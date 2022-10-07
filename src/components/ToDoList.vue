<script setup>
    import {ref} from "vue"
    import {computed} from "vue"

    const list = ref([]);
    const input = ref("");

    const filter = ref("")

    const filteredList = computed(() => {
    let result = [];
    for (let i = 0; i < list.value.length; i++) {
        if (list.value[i].toLowerCase().includes(filter.value.toLowerCase())) {
            result.push(list.value[i]);
        }
    }
    return result;
});

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

        <input v-model="input" @keyup.enter="add()" placeholder="Item"/>
        <!--<button @click="add">
            Add
        </button>--> <br><br>
        <input v-model="filter" type="text" placeholder="Filterlist">
        
        <ul>
            <li v-for="(item, index) in filteredList" :key="item">
                {{index}} - {{item}} &nbsp &nbsp
                    <button @click="remove(index)">X</button>
            </li>

        </ul>
    </div>
  </template>
  



