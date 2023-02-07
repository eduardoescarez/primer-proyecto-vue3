<script setup>
    const name = "Vue dinámico"

// metodo
    const cliqueador = (message) =>{
        console.log(message)
    }

</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <button v-on:click="cliqueador('texto uno')">Activame</button>
    <button @click="cliqueador('texto dos')">Activame</button>


</template>

<style>
h1{
    color: red;
}
</style>