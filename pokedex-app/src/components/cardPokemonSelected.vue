
<script setup>
const pokemon = defineProps(['name', 'xp', 'height', 'weight', 'img'])

</script>

<template>
    <div class="card CardPokemonSelected">

        <img v-if="pokemon.name" :src="pokemon.img" class="card-img-top pt-2" :alt="pokemon.name">

        <img v-else src="../assets/egg_pokemon.svg" class="card-img-top pt-2" alt="???">

        <div class="card-body">
            <h5 class="card-title text-center">{{ pokemon.name || '???' }}</h5>
            <hr>
            <div class="col">
                <section>
                    <strong>XP: </strong>
                    <span>{{ pokemon.xp }}</span>
                </section>

                <section>
                    <strong>Altura: </strong>
                    <span>{{ (pokemon.height * 0.1).toFixed(1) }} m</span>
                </section>

                <section>
                    <strong>Peso: </strong>
                    <span>{{ (pokemon.weight * 0.1).toFixed(1) }} kg</span>
                </section>

            </div>
        </div>
    </div>
</template>

<style scoped>
.CardPokemonSelected {
    height: 440px;
    background: rgb(67, 82, 84);
    background: linear-gradient(90deg, #5b29e67a 0%, #ce8c1949 79%);
}

.CardPokemonSelected img {
    height: 250px;
}

@media (max-width: 600px) {
    .CardPokemonSelected {
        height: 340px;
        width: 65%;
        margin: 0 auto 10px auto;
    }

    .CardPokemonSelected img {
        height: 150px;
    }
}
</style>