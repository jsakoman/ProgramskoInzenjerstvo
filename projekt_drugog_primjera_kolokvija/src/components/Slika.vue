<script setup>
const props = defineProps({
  slikar: String,
  godina: Number,
  naslov: String,
  slika: String
})

function starost() {
  const now = new Date().getFullYear()
  return now - props.godina
}
</script>

<template>
  <div>
    <img :src="props.slika" height="100" />
    <p><strong>Naslov: {{ props.naslov }}</strong></p>
    <p><strong>Starost: {{ starost() }} godina</strong></p>
    <p><strong>Slikar: {{ props.slikar }}</strong></p>
  </div>
</template>