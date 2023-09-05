<script setup>
    import cars from "../data/cars.json"
    import { RouterLink } from "vue-router";
</script>

<template>
    <div>
        <h1>Home View</h1>
       <!-- the backticks used here are called template literals  -->
        <div class="cars">
            <RouterLink :to="`/cars/${car.id}`" v-for="car in cars"
            :key="car.id" >{{car.name}}</RouterLink>
        </div>
    </div>
</template>

<style scoped>
    .cars {
        display: flex;
    }

    .cars a {
        text-decoration: none;
        color: coral;
        width: 100%;
        box-shadow: 1px 1px 1px rgba(194, 181, 181, 0.388);
        margin: 10px;
    }
</style>