<script setup>
    import { ref } from 'vue';

    const sportasi = ref([
        {
            ime: 'Ivan', 
            disciplina: 'plivanje', 
            godine: 25, 
            natjecanja: ['Olimpijske igre', 'Svjetsko prvenstvo']
        },
        {
            ime: 'Ana', 
            disciplina: 'atletika', 
            godine: 30, 
            natjecanja: ['Svjetsko prvenstvo', 'Europsko prvenstvo', 'Olimpijske igre']
        },
        {
            ime: 'Marko', 
            disciplina: 'odbojka', 
            godine: 22, 
            natjecanja: ['Europsko prvenstvo']
        }
    ])
</script>

<template>
    <div>
        ZADATAK 2
    </div>
</template>

<style scoped>

</style>