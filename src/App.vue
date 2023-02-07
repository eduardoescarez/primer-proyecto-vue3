<script setup>
    import { ref, computed } from 'vue'

    const name = "Vue dinámico"

    let counter = ref(0)

    let arrayNumeros = ref([])

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
        arrayNumeros.value.push(counter.value)
    }

    const favoritosLimpiar = computed(() => {
        for (let i = arrayNumeros.value.length; i > 0; i--) 
            {arrayNumeros.value.pop();}
    })

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

    const statusNumber = computed(() => {
        const number = arrayNumeros.value.find((num) => num === counter.value);
        return number || number === 0;
    })

// metodo


</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <h2 :class="classCounter">{{ counter }}</h2>

    <h3>Números favoritos</h3>
    <span v-for="numero, index in arrayNumeros" :key="index">{{ numero }} &nbsp;</span>
    <br/>

    <button @click="aumentar">Aumentar</button> <button @click="disminuir">Disminuir</button> <button @click="resetear">Resetear</button> <button @click="favoritos" :disabled="statusNumber">Agregar a Favoritos</button> <button @click="favoritosLimpiar">Limpiar favoritos</button>



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