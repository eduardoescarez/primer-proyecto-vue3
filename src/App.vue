<script setup>
const name = "Vue dinámico"
const arrayColores = ["blue", "red", "peru"]
const activo = false
const arrayEmojiFrutas = ["🍎", "🍌", "🍉", "🍓", "🍒"]
const arrayFrutas = [
        {
            name: "Manzana",
            price: "$1.00",
            description: "Una manzana",
        },
        {
            name: "Pera",
            price: "$2.00",
            description: "Una pera",
        },
        {
            name: "Naranja",
            price: "$3.00",
            description: "Una naranja",
        },
    ];
const objetoFruta = {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
};

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
        <li v-for="(fruta, index) in arrayEmojiFrutas" :key="index">{{ index }} - {{ fruta }}</li>
    </ul>

    <br/>

    <ul>
        <li v-for="(fruta) in arrayFrutas" :key="fruta.name">{{ fruta.name }} - {{ fruta.price }} - {{ fruta.description }}</li>
    </ul>

    <br/>

    <ul>
        <li v-for="(value, propiedad, index) in objetoFruta" :key="value">{{ propiedad }} : {{ value }} - {{ index }}</li>
    </ul>


</template>

<style>
h1{
    color: red;
}
</style>