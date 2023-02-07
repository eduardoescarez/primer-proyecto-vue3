<script setup>
    const name = "Vue dinámico"

// metodo
    const cliqueador = (message) =>{
        console.log(message)
    }

</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <button @click.right.prevent="cliqueador('Mensaje desde derecha')"> Click right </button>
    <button @click.middle="cliqueador('Mensaje desde centro')"> Click center </button>
    <button @click="cliqueador('Mensaje desde izquierda')"> Click left </button>

</template>

<style>
h1{
    color: red;
}
</style>