<script setup>
const props = defineProps(["name", "id"]);
const emit = defineEmits(["remove"]);
</script>

<template>
    <li>
    {{name}} &nbsp
    <button @click="emit('remove',  id )">x</button>
    </li> <br>
</template>
