
<script setup>
const pokemon = defineProps(['name', 'xp', 'height', 'img'])

</script>

<template>
    <div class="card CardPokemonSelected">
        <img :src="pokemon.img" height="150" class="card-img-top pt-2" :alt="pokemon.name">
        <div class="card-body">
            <h5 class="card-title text-center">{{ pokemon.name }}</h5>
            <hr>
            <div class="row">
                <section class="col">
                    <strong>XP: </strong>
                    <span>{{ pokemon.xp }}</span>
                </section>

                <section class="col">
                    <strong>altura: </strong>
                    <span>{{ pokemon.height }}m</span>
                </section>
            </div>
        </div>
    </div>
</template>

<style scoped>
.CardPokemonSelected {
    height: 450px;
    background: rgb(67, 82, 84);
    background: linear-gradient(90deg, #5b29e67a 0%, #ce8c1949 79%);
}
</style>