<script setup>
    const name = "Vue dinámico"

    let counter = 0

    const sumador = () =>{
        counter++
        console.log(counter)
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