<template>
    <img :src="pokemon.image" :alt="pokemon.name" class="w-full">
    <div class="p-4">
        <h2 class="text-xl font-semibold text-center">{{ pokemon.name }}</h2>
        <div class="mt-2">
            <div class="flex justify-center">
                <div v-for="type in pokemon.apiTypes" :key="type.name" class="inline-block mr-2">
                    <img :src="type.image" :alt="type.name" class="w-6 h-6">
                </div>
            </div>
        </div>
    </div>
    <div class="flex">
        <button class="w-full py-2 bg-emerald-600 text-white font-semibold" @click="showPokemon(pokemon.id)">Show</button>
        <button class="w-full py-2 bg-emerald-600 text-white font-semibold">Add to Pokedex</button>
    </div>
</template>

<script setup>
    defineProps({
        pokemon: Object
    })

    const router = useRouter();

    const idPokemon = useState('idPokemon', () => [])

    function showPokemon(id) {
        idPokemon.value = id;
        router.push(`/${id}`);
    }
</script>