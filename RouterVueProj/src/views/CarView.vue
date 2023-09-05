<script setup>
    import { useRoute, useRouter, RouterView } from 'vue-router';
    import cars from '../data/cars.json'
    import ContactView from './ContactView.vue'    
    /* 
    DIFFERENCE BETWEEN useRoute AND useRouter:
    useRoute is a composible that allows us to extract info about the current path that we are in but we cannot adjust our path

    useRouter is also a composible which allows us adjust/ update our path
    */
    const route = useRoute()
    const router = useRouter()

    const carId = parseInt(route.params.id)

    const car = cars.find(c => c.id === parseInt (route.params.id))

</script>

<template> 
    <div>
        <h1>Car View</h1>
        <p>{{car.name}}</p>
        <p>{{car.year}}</p>
        <p>{{car.price}}</p>
        <button @click="router.push(`/cars/${carId}/contact`)">Click for Contact</button>
        <RouterView /> 
    </div>
</template>