<script setup>
</script>

<template>
  <!-- Cijela stranica s gradijent pozadinom -->
  <div class="min-h-screen bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 p-8">
    
    <!-- Naslov -->
    <h1 class="text-center text-2xl font-bold text-silver-300 mb-4">
      Pozdrav, ja sam 
      <span class="font-extrabold text-yellow-500">Josip Sakoman</span>
    </h1>

    <!-- Horizontalna crta -->
    <hr class="border-t-2 border-sky-700 mb-8">

    Moji omiljeni filmovi
    <!-- Pravokutnici -->
    <div class="flex justify-between space-x-4 mb-4">
      <div class="flex flex-col items-center">
        <div class="w-[320px] h-[480px] bg-zinc-800/90 border-sky-700 border-6 flex items-center justify-center">
          <p class="text-lime-300 text-4xl font-bold uppercase">POSTER</p>
        </div>
        <p class="text-lime-300 mt-2">Naslov filma 1</p>
      </div>

      <div class="flex flex-col items-center">
        <div class="w-[320px] h-[480px] bg-zinc-800/90 border-sky-700 border-6 flex items-center justify-center">
          <p class="text-lime-300 text-4xl font-bold uppercase">POSTER</p>
        </div>
        <p class="text-lime-300 mt-2">Naslov filma 2</p>
      </div>

      <div class="flex flex-col items-center">
        <div class="w-[320px] h-[480px] bg-zinc-800/90 border-sky-700 border-6 flex items-center justify-center">
          <p class="text-lime-300 text-4xl font-bold uppercase">POSTER</p>
        </div>
        <p class="text-lime-300 mt-2">Naslov filma 3</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
