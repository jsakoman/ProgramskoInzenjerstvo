<script setup>
import podaci from './assets/podaci.json'

const slike = podaci.slike
const proizvodi = podaci.proizvodi
const korisnik = podaci.korisnik
</script>

<template>
  <div :class="korisnik.jeAdmin ? 'text-blue-500' : 'text-black'" class="p-4">
    <h2 class="text-xl font-bold mb-2">Korisnicki podaci:</h2>
    <p><strong>Ime:</strong> {{ korisnik.osobni_podaci.ime }}</p>  
    <p><strong>Prezime:</strong> {{ korisnik.osobni_podaci.prezime }}</p>  
    <p><strong>Adresa:</strong> {{ korisnik.osobni_podaci.adresa.ulica }} {{ korisnik.osobni_podaci.adresa.broj }}, {{ korisnik.osobni_podaci.adresa.grad }}</p>  
    <p><strong>Telefon:</strong> {{ korisnik.osobni_podaci.broj_telefona }}</p>  
  </div>

  <h2 class="text-xl font-bold mb-2">Sadržaj košarice</h2>
  
  <!-- JABUKA -->
  <div class="mb-4">
    <p><strong>Naziv:</strong> {{ korisnik.kosarica[0].naziv }}</p>
    <img :src="slike.Jabuka" alt="Jabuka" class="w-10 h-10" />
    <p><strong>Kolicina:</strong> {{ korisnik.kosarica[0].kolicina }}</p>
  </div>

    <!-- MRKVA -->
    <div class="mb-4">
      <p><strong>Naziv:</strong> {{ korisnik.kosarica[1].naziv }}</p>
      <img :src="slike.Mrkva" alt="Mrkva" class="w-10 h-10" />
      <p><strong>Kolicina:</strong> {{ korisnik.kosarica[1].kolicina }}</p>
    </div>

    <!-- SIR -->
    <div class="mb-4">
      <p><strong>Naziv:</strong> {{ korisnik.kosarica[2].naziv }}</p>
      <img :src="slike.Sir" alt="Sir" class="w-10 h-10" />
      <p><strong>Kolicina:</strong> {{ korisnik.kosarica[2].kolicina }}</p>
    </div>    

    <!-- KRUH -->
    <div class="mb-4">
      <p><strong>Naziv:</strong> {{ korisnik.kosarica[3].naziv }}</p>
      <img :src="slike.Kruh" alt="Kruh" class="w-10 h-10" />
      <p><strong>Kolicina:</strong> {{ korisnik.kosarica[3].kolicina }}</p>
    </div>    



</template>

<style scoped>
</style>
