<template>
    <div class="flex mx-10 my-3">
        <input type="text" class="rounded-l-md py-1 text-center bg-gray-200 border-2 border-black flex-grow border-e-0 focus:outline-none focus:ring-0" v-model="pokeName">
        <button class="rounded-r-md bg-gray-200 border-2 border-black border-s-0">
            <Icon name="mingcute:search-3-line" width="32" height="32" />
        </button>
    </div>
</template>

<script setup>
    const pokeName = ref('');
</script>