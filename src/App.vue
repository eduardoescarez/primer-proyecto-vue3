<script setup>
    import { ref, computed } from 'vue'

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

    const favoritos = () =>{
        
    }

    const classCounter = computed(() => {
        if (counter.value === 0) {
            return "zero"
        }
        if (counter.value > 0){
            return "positive"
        }
        if (counter.value < 0){
            return "negative"
        }
    })

// metodo


</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <h2 :class="classCounter">{{ counter }}</h2>

    <button @click="aumentar">Aumentar</button> <button @click="disminuir">Disminuir</button> <button @click="resetear">Resetear</button> <button @click="favoritos">Favoritos</button>



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
    .zero {
        color: peru;
    }
</style>