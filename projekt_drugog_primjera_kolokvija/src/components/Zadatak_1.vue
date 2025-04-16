<script setup>
import { ref } from 'vue'

const broj1 = ref('')
const broj2 = ref('')
const operacija = ref('')

function provjeraOperacije() {
    const dozvoljeneOperacije = ['zbrajanje', 'oduzimanje', 'mnozenje', 'dijeljenje'];
    return dozvoljeneOperacije.includes(operacija.value);
}

</script>

<template>
    <div>
        ZADATAK 1
    </div>
</template>

<style scoped>

</style>