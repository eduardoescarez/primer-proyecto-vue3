<script setup>
    import { ref } from 'vue'

    const name = "Vue dinámico"

    let counter = ref(0)

    const aumentar = () =>{
        counter.value ++
    }

    const disminuir = () =>{
        counter.value --
    }

    const resetear = () =>{
        counter.value = 0
    }

// metodo


</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <h2 :class="counter > 0 ? 'positive' : 'negative'">{{ counter }}</h2>

    <button @click="aumentar">Aumentar</button> <button @click="disminuir">Disminuir</button> <button @click="resetear">Resetear</button>


</template>

<style>
    h1{
        color: red;
    }
    .positive{
        color: green;
    }
    .negative {
        color: red;
    }
</style>