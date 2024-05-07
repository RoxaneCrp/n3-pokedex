<template>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 mx-auto w-5/6">
        <div v-for="pokemon in team" :key="pokemon.id" class="bg-white rounded-lg shadow-md overflow-hidden">
            <PokeCard :pokemon="pokemon" />
        </div>
    </div>
</template>

<script setup>
    const team = useState('team')
</script>