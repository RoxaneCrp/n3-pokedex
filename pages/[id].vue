<template>
    <div class="max-w-3xl mx-auto">
      <h1 class="text-3xl font-semibold text-center">{{ data.name }}</h1>
      <div class="flex justify-center">
        <img :src="data.image" :alt="data.name" class="w-48 h-48 mt-4">
      </div>
      <div class="mt-8">
        <h2 class="text-xl font-semibold">Types:</h2>
        <div class="flex justify-center mt-2">
          <span v-for="type in data.apiTypes" :key="type.name" class="inline-block mx-2 py-1 px-3 bg-gray-200 rounded-full text-sm">{{ type.name }}</span>
        </div>
      </div>
      <div class="mt-8">
        <h2 class="text-xl font-semibold">Stats:</h2>
        <ul class="mt-2">
          <li v-for="(value, key) in data.stats" :key="key" class="mb-2">{{ key }}: {{ value }}</li>
        </ul>
      </div>
      <div class="mt-8">
        <h2 class="text-xl font-semibold">Résistances:</h2>
        <ul class="mt-2">
          <li v-for="resistance in data.apiResistances" :key="resistance.name" class="mb-2">{{ resistance.name }} - {{ resistance.damage_relation }} ({{ resistance.damage_multiplier }})</li>
        </ul>
      </div>
      <div class="mt-8" v-if="data.apiEvolutions.length > 0">
        <h2 class="text-xl font-semibold">Évolutions:</h2>
        <ul class="mt-2">
          <li v-for="evolution in data.apiEvolutions" :key="evolution.pokedexId" class="mb-2">{{ evolution.name }}</li>
        </ul>
      </div>
    </div>
  </template>
  
<script setup>  
    const idPokemon = useState('idPokemon')

    const { data} = useFetch('https://pokebuildapi.fr/api/v1/pokemon/'+idPokemon.value, {});
</script>