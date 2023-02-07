<script setup>
const name = "Vue dinámico"
const styleColor = "color: blue;"
const arrayColores = ["blue", "red", "peru"]
const activo = false
const arrayFrutas = ["🍎", "🍌", "🍉", "🍓", "🍒"]
</script>

<template>
    <h1>Hola {{ name.toUpperCase() }}</h1>
    <h2>{{ arrayColores }}</h2>
    <h2 :style="`color: ${arrayColores[2]}`">Soy azul</h2>
    <p v-if="activo === true">Estoy activo</p>
    <p v-else-if="activo === false">Estoy inactivo</p>
    <p v-else>Estoy indeciso</p>
    <p v-show="activo">Estoy activo v-show</p>

    <ul>
        <li v-for="(fruta, index) in arrayFrutas" :key="index">{{ index }} - {{ fruta }}</li>
    </ul>

    <br/>
</template>

<style>
h1{
    color: red;
}
</style>