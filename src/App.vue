<script setup>
    const name = "Vue dinámico"

// metodo
    const cliqueador = () =>{
        console.log ("Un click recibido 😅")
    }

</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <button v-on:click="cliqueador">Activame</button>


</template>

<style>
h1{
    color: red;
}
</style>