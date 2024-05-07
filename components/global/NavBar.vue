<template>
    <div class="flex justify-center">
        <ul class="inline-flex  gap-4">
            <li v-for="item in menuItems" :key="item.name">
                <NuxtLink :to="item.path" v-slot="{ isActive }">
                    <div :class="{ 'bg-green-300': isActive }" class="bg-green-100 rounded-md px-4 py-2">
                        <Icon :name="item.icon" width="32" height="32"  color="black" />
                        {{ item.name }}
                    </div>
                </NuxtLink>
            </li>
        </ul>
    </div>
</template>

<script setup>
const menuItems = [
    { name: 'Catalogue', path: '/', icon: 'arcticons:pokemon-tcg-live' },
    { name: 'Equipe', path: '/team', icon: 'ic:baseline-catching-pokemon' },
]
</script>