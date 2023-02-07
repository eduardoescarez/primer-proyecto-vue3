<script setup>
    import { ref } from 'vue'

    const name = "Vue dinámico"

    let counter = ref(0)

    const sumador = () =>{
        counter.value ++
    }

// metodo


</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <h2>{{ counter }}</h2>

    <button @click="sumador">Aumentar</button>


</template>

<style>
h1{
    color: red;
}
</style>