<script setup>
import podaci from './assets/podaci.json'

const slike = podaci.slike
const proizvodi = podaci.proizvodi
const korisnik = podaci.korisnik

function dohvatiCijenu(naziv) {
  const proizvod = proizvodi.find(p => p.naziv === naziv);
  return proizvod ? proizvod.cijena : 0;
}

function ukupnoPoArtiklu(naziv) {
  const stavka = korisnik.kosarica.find(s => s.naziv === naziv);
  const cijena = dohvatiCijenu(naziv);
  return stavka ? cijena * stavka.kolicina : 0;
}

function najskupljaStavka() {
  let maxStavka = null;
  let maxCijena = 0;

  korisnik.kosarica.forEach(stavka => {
    const ukupno = ukupnoPoArtiklu(stavka.naziv);
    if (ukupno > maxCijena) {
      maxCijena = ukupno;
      maxStavka = stavka.naziv;
    }
  });

  return maxStavka;
}

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
  <div class="mb-4 p-4 rounded"
    :class="najskupljaStavka() === korisnik.kosarica[0].naziv ? 'border-red-500 bg-red-100 border' : 'border-gray-300 border'">
    <p><strong>Naziv:</strong> {{ korisnik.kosarica[0].naziv }}</p>
    <img :src="slike.Jabuka" alt="Jabuka" class="w-10 h-10" />
    <p><strong>Kolicina:</strong> {{ korisnik.kosarica[0].kolicina }}</p>
    <p><strong>Cijena:</strong> {{ dohvatiCijenu(korisnik.kosarica[0].naziv).toFixed(2) }} €</p>
    <p><strong>Ukupno:</strong> {{ ukupnoPoArtiklu(korisnik.kosarica[0].naziv).toFixed(2) }}€</p>
  </div>

  <!-- MRKVA -->
  <div class="mb-4 p-4 rounded"
    :class="najskupljaStavka() === korisnik.kosarica[1].naziv ? 'border-red-500 bg-red-100 border' : 'border-gray-300 border'">
    <p><strong>Naziv:</strong> {{ korisnik.kosarica[1].naziv }}</p>
    <img :src="slike.Mrkva" alt="Mrkva" class="w-10 h-10" />
    <p><strong>Kolicina:</strong> {{ korisnik.kosarica[1].kolicina }}</p>
    <p><strong>Cijena:</strong> {{ dohvatiCijenu(korisnik.kosarica[1].naziv).toFixed(2) }} €</p>
    <p><strong>Ukupno:</strong> {{ ukupnoPoArtiklu(korisnik.kosarica[1].naziv).toFixed(2) }}€</p>
  </div>

  <!-- SIR -->
  <div class="mb-4 p-4 rounded"
    :class="najskupljaStavka() === korisnik.kosarica[2].naziv ? 'border-red-500 bg-red-100 border' : 'border-gray-300 border'">
    <p><strong>Naziv:</strong> {{ korisnik.kosarica[2].naziv }}</p>
    <img :src="slike.Sir" alt="Sir" class="w-10 h-10" />
    <p><strong>Kolicina:</strong> {{ korisnik.kosarica[2].kolicina }}</p>
    <p><strong>Cijena:</strong> {{ dohvatiCijenu(korisnik.kosarica[2].naziv).toFixed(2) }} €</p>
    <p><strong>Ukupno:</strong> {{ ukupnoPoArtiklu(korisnik.kosarica[2].naziv).toFixed(2) }}€</p>
  </div>    

  <!-- KRUH -->
  <div class="mb-4 p-4 rounded"
    :class="najskupljaStavka() === korisnik.kosarica[3].naziv ? 'border-red-500 bg-red-100 border' : 'border-gray-300 border'">
    <p><strong>Naziv:</strong> {{ korisnik.kosarica[3].naziv }}</p>
    <img :src="slike.Kruh" alt="Kruh" class="w-10 h-10" />
    <p><strong>Kolicina:</strong> {{ korisnik.kosarica[3].kolicina }}</p>
    <p><strong>Cijena:</strong> {{ dohvatiCijenu(korisnik.kosarica[3].naziv).toFixed(2) }} €</p>
    <p><strong>Ukupno:</strong> {{ ukupnoPoArtiklu(korisnik.kosarica[3].naziv).toFixed(2) }}€</p>
  </div>    
</template>

<style scoped>
</style>
