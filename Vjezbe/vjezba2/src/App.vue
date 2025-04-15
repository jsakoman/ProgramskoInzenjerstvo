<script setup>
import podaci from './assets/podaci.json'

const slike = podaci.slike
const proizvodi = podaci.proizvodi
const korisnik = podaci.korisnik
</script>

<template>
  <div>
    <p><strong>Ime:</strong> {{ korisnik.osobni_podaci.ime }}</p>  
    <p><strong>Prezime:</strong> {{ korisnik.osobni_podaci.prezime }}</p>  
    <p><strong>Adresa:</strong> {{ korisnik.osobni_podaci.adresa.ulica }} {{ korisnik.osobni_podaci.adresa.broj }}, {{ korisnik.osobni_podaci.adresa.grad }}</p>  
    <p><strong>Telefon:</strong> {{ korisnik.osobni_podaci.broj_telefona }}</p>  
  </div>

</template>

<style scoped>
</style>
