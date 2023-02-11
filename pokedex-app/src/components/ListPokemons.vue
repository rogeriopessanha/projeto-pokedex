
<script setup>
const pokemon = defineProps(['name', 'urlBaseSvg'])

</script>

<template>
    <div class="col-4">
        <div class="card mb-3 cardListPokemon">
            <p class="text-center">{{ pokemon.name }}</p>
            <img :src="urlBaseSvg" class="card-img-top" alt="..." height="60">
        </div>
    </div>
</template>


<style scoped>
.cardListPokemon {
    background: rgb(67,82,84);
background: linear-gradient(90deg, rgba(67,82,84,0.47911547911547914) 0%, rgba(47,73,52,0.28501228501228504) 79%);
cursor: pointer;
}

.cardListPokemon:hover {
    background: rgb(67,82,84);
    background: linear-gradient(90deg, rgba(67,82,84,0.47911547911547914) 0%, rgba(47,73,52,0.773955773955774) 79%);
}

.cardListPokemon img:hover {
    padding: .1rem;
}
</style>