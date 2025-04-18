<script setup>
import Slika from './Slika.vue';

    const galerija = [    
        {
            slikar: "Pablo Picasso",
            godina: 1903,
            naslov: "The Old Guitarist",
            slika: "/src/assets/slike/The Old Guitarist.png"
        },
        {
            slikar: "Vincent van Gogh",
            godina: 1886,
            naslov: "Le Moulin de Blute-Fin",
            slika: "/src/assets/slike/Le Moulin de Blute-Fin.png"
        },
        {
            slikar: "Hokusai",
            godina: 1890,
            naslov: "Courtesan Asleep",
            slika: "/src/assets/slike/Courtesan Asleep.png"
        },
    ];
</script>

<template>
    <div>
        <h1>ZADATAK 3</h1>
        <Slika v-for="(item,index) in galerija" :key="index"
            :slikar="item.slikar"
            :godina="item.godina"
            :naslov="item.naslov"
            :slika="item.slika" />

    </div>
</template>

<style scoped>

</style>