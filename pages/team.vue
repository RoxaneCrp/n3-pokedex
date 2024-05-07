<template>
    <div class="flex justify-center pt-2">
        <img src="/public/pokedex.png" alt="pokedex logo" class="size-24">
    </div>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 mx-auto w-5/6">
        <div v-if="team.length" v-for="pokemon in team" :key="pokemon.id" class="bg-white rounded-lg shadow-md overflow-hidden">
            <PokeCard :pokemon="pokemon" />
        </div>
        <div v-else class="text-center py-4">
            <p>Aucun Pokémon dans l'équipe.</p>
        </div>
    </div>
</template>

<script setup>
    const team = useState('team')
</script>