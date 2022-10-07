<script setup>

import {ref} from "vue"

import {computed} from "vue"

let number = ref(2);
let number_quadriert = computed(function() {
    return number.value * number.value;
});

</script>

<template>
    <h1>Computed Demo</h1>
    <p>Zahl: {{number}} </p>
    <p>Quadriert: {{number_quadriert}}</p>
</template>
<!---->