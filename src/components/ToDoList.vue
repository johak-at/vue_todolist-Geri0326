<script setup>
import { ref } from "vue";
import { computed } from "vue";
import ToDo from './ToDo.vue';
const list = ref([]);
const newItem = ref("");
const filter = ref("");
const filteredList = computed(() => {
    let result = [];
    for (let i = 0; i < list.value.length; i++) {
        if (list.value[i].name.toLowerCase().includes(filter.value.toLowerCase())) {
            result.push(list.value[i]);
        }
    }
    return result;
});
function add() {
    list.value.push({
        id: Date.now().toString(16),
        name: newItem.value,
    });
    newItem.value = "";
}
function remove(id) {
        for(let i = 0; i < list.value.length; i++) {
            if (list.value[i].id === id) {
                list.value.splice(i, 1);
            }
                
            }
            console.log("test")
        }

function test() {
    console.log("test");
    
}
</script>

<template>
    <div>
        <h1>ToDoList</h1>
        <input @keyup.enter="add" v-model="newItem" />
        <br /><br />
        <input type="text" placeholder="filter list" v-model="filter" />
        <ul>
            <!--use ToDo.vue to add remove button-->
            <ToDo v-for="item in filteredList" :key="item.id" :name="item.name" :id="item.id" @remove="remove" />
        </ul>


    </div>
</template>