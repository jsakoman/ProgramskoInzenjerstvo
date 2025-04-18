<script setup>
defineProps(
    {
        slikar: String,
        godina: Number,
        naslov: String,
        slika: String
})
</script>

<template>
    <div>
        <img :src="slika" height="100"/>
        <p><strong>Naslov: {{ naslov }}</strong></p>
        <p><strong>Godina: {{ godina }}</strong></p>
        <p><strong>Slikar: {{ slikar }}</strong></p>
    </div>
</template>

<style scoped>
</style>