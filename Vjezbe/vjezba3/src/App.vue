<script setup>
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

  </div>
</template>

<style scoped>
</style>
