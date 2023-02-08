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

    const favoritosBloquear = computed(() => {
        const busquedaFavorito = arrayNumeros.value.find((num) => num === counter.value);
        // return busquedaFavorito || busquedaFavorito === 0;
        if (busquedaFavorito === 0) return true
        return busquedaFavorito ? true : false
    })

// metodo


</script>

<template>
    <div class="container">
    <h1>Hola {{ name.toUpperCase() }}</h1>

    <h2 :class="classCounter">{{ counter }}</h2>

    <h3>Números favoritos</h3>
    <span v-for="(numero, index) in arrayNumeros" :key="index">{{ numero }} &nbsp;</span>
    <br/>

    <div class="btn-group">
        <button @click="aumentar" class="btn btn-primary">Aumentar</button>
        <button @click="disminuir" class="btn btn-warning">Disminuir</button>
        <button @click="resetear" class="btn btn-danger">Resetear</button>
        <button @click="favoritos" :disabled="favoritosBloquear" class="btn btn-success">Agregar a Favoritos</button>
        <button @click="favoritosLimpiar" class="btn btn-danger">Limpiar favoritos</button>
    </div>

    </div>
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