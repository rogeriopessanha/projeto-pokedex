
<script setup>
const pokemon = defineProps(['name', 'urlBaseSvg'])

</script>

<template>
    <div class="col-4">
        <div class="card mb-3">
            <p class="text-center">{{ pokemon.name }}</p>
            <img 
            :src="urlBaseSvg" class="card-img-top" alt="..."
            height="60"
            >
        </div>
    </div>
</template>


<style>

</style>