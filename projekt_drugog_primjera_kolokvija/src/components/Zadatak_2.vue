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
        <h1 class="text-2xl font-bold">ZADATAK 2</h1>

        <div v-for="(sportas, index) in sportasi" :key="index" border>
            <div class="border mb-4 bg-blue-50">
            <p><strong>Ime:</strong> {{ sportas.ime }}</p>
            <p><strong>Disciplina:</strong> {{ sportas.disciplina }}</p>
            <p><strong>Starost:</strong> {{ sportas.godine }}</p>
            <p><strong>Natjecanja:</strong></p>
            <ul>
                <li v-for="(natjecanje, nIndex) in sportas.natjecanja" :key="nIndex">
                    {{ natjecanje }}
                </li>
            </ul>
        </div>

        </div>
    </div>
</template>

<style scoped>

</style>