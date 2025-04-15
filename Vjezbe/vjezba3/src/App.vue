<script setup>
import { ref } from 'vue';

const naziv = ref('');
const cijena = ref(0);
const kosarica = ref([]);

function dodajProizvod() {
  if (naziv.value && cijena.value > 0) {
    const postoji = kosarica.value.find(stavka => stavka.naziv === naziv.value);
    if (postoji) {
      postoji.kolicina += 1;
    } else { 
      kosarica.value.push({ naziv: naziv.value, cijena: cijena.value, kolicina: 1})
    }
    naziv.value = '';
    cijena.value = 0;
  }
}

</script>

<template>
  <div class="container mx-auto p-6">

      <h1 class="font-bold mb-4">Kosarica</h1>

      <!-- Unos novog proizvoda-->
      <div class="mb-6">
        <input v-model="naziv" type="text" placeholder="Naziv proizvoda" class="input-field mb-2 p-2 border rounded w-full"/>
        <input v-model="cijena" type="number" placeholder="Cijena proizvoda" min="0" class="input-field mb-2 p-2 border w-full"/>
        <button @click="dodajProizvod" :disabled="!naziv || cijena <= 0" class="bg-blue-500 text-white px-4 py-2  disabled:bg-gray-500">Dodaj artikl</button>
      </div> 


      <!-- Kosarica -->
      <div v-if="kosarica.length === 0" class="text-gray-500"> Kosarica je prazna!</div>
      <div v-else>
        <ul>
          <li v-for="(stavka, index) in kosarica" :key="index" class="mb-4">
            <div class="flex justify-between items-center border rounded bg-gray-100">
              <div>
                <h3 class="p-6"> {{ stavka.naziv }}</h3>
                <p>Cijena: {{ stavka.cijena }}€</p>
              </div>
              <div>
                <p>Kolicina: {{  stavka.kolicina }}</p>
                <button @click="promijeniKolicinu(index, -1)" class="bg-red-500 text-white px-2 py-1">-</button>
                <button @click="promijeniKolicinu(index, 1)" class="bg-green-500 text-white px-2 py-1">+</button>
                <button @click="ukloniProizvod(index)" class="bg-gray-500 text-white px-4 py-1">Ukloni</button>
              </div>
            </div>
          </li>
        </ul>
      </div>

  </div>
</template>

<style scoped>
</style>
