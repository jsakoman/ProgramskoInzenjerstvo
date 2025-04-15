<template>
    <nav class="sticky top-0 w-full flex gap-4 flex-wrap items-center justify-around bg-[#070F2B]/25 backdrop-blur-sm py-2 px-8 rounded-lg">
        <div 
            v-for="link in links" 
            :key="link.name" 
            class="text-sm z-10 relative transition" 
            @click="setActiveLink(link.name)"
            :class="[
                link.name === activeLink ? 'underline text-purple-100' : 'cursor-pointer text-indigo-300 text-sm hover:text-indigo-200 hover:scale-105', 
                link.active ? '' : 'text-indigo-500/50 text-sm pointer-events-none font line-through'
            ]">
            {{ link.name }} 
            <b v-if="link.name === activeLink" class="text-purple-400 -z-[5] absolute -left-0.5 blur-sm">
                {{ link.name }}
            </b>
        </div>
    </nav>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
    activeLink: {
        type: String,
        required: true
    }
})

const emit = defineEmits()

const links = [
    { name: "POČETNA", active: true },
    { name: "SLIKA", active: true },
    { name: "ZVUK", active: false },
    { name: "GRAFIKA", active: true },
    { name: "MODEL", active: false },
    { name: "VIDEO", active: false }
]

const setActiveLink = (linkName) => {
    emit('updateActiveLink', linkName)
}
</script>