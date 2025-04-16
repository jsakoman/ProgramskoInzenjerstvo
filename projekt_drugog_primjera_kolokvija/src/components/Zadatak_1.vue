<script setup>
import { ref, computed } from 'vue'

const broj1 = ref('')
const broj2 = ref('')
const operacija = ref('')

// computed funkcija koristi caching (privremena pohrana podataka) da ne mora konstantno vrtiti u pozadini nego samo kod promjene parametara se funkcija izvrsi
const provjeraOperacije = computed(() => {
  const dozvoljeneOperacije = ['zbrajanje', 'oduzimanje', 'mnozenje', 'dijeljenje'];
  return dozvoljeneOperacije.includes(operacija.value);
});

</script>

<template>
    <div class="flex items-center justify-center bg-gray-100">
        <div class="p-4 max-w bg-white">
            <h1 class="text-2xl font-bold">ZADATAK 1</h1>

            <div class="flex flex-col">
                <label>Broj 1:
                    <input v-model="broj1" type="number" class="border p-2"/>
                </label>
                <label>Broj 2:
                    <input v-model="broj2" type="number" class="border p-2"/>
                </label>
                <label>Operacija (zbrajanje, oduzimanje, mnozenje, dijeljenje):
                    <input v-model="operacija" type="text" class="border p-2"/>
                </label>

                <div v-if="!provjeraOperacije">
                    <p class="text-red-500">Nepoznata operacija!</p>
                </div>
                <div v-else>
                    <p class="text-green-500">
                        Rezultat:{{ 
                            operacija === 'zbrajanje' ? Number(broj1) + Number(broj2) :
                            operacija === 'oduzimanje' ? Number(broj1) - Number(broj2) :
                            operacija === 'mnozenje' ? Number(broj1) * Number(broj2) :
                            operacija === 'dijeljenje' ? 
                                (Number(broj2) != 0 ? Number(broj1) / Number(broj2) : ' Dijeljenje s 0 nije moguce!')
                            : ''
                            }}
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>