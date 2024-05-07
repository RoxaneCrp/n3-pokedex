<template>
    <div class="flex justify-center pt-2">
        <img src="/public/pokedex.png" alt="pokedex logo" class="size-24">
    </div>

    <SearchBar />

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4 mx-auto w-5/6">
        <div v-for="pokemon in data" :key="pokemon.id" class="bg-white rounded-lg shadow-md overflow-hidden">
            <PokeCard :pokemon="pokemon" />
        </div>
    </div>
</template>

<script setup>
    const { data} = useFetch('https://pokebuildapi.fr/api/v1/pokemon/limit/10', {});
</script>