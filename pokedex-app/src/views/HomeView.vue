<script setup>
import { onMounted, reactive, ref, computed } from 'vue';
import ListPokemons from '../components/ListPokemons.vue'
import cardPokemonSelected from '../components/cardPokemonSelected.vue'

let urlBaseSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/")

let pokemons = reactive(ref())
let searchPokemonField = ref('')
let pokemonSelected = reactive(ref())

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=251&offset=0")
    .then(res => res.json())
    .then(res => pokemons.value = res.results)
})

const pokemonsFiltered = computed(() => {
  if (pokemons.value && searchPokemonField.value) {
    return pokemons.value.filter(pokemon =>
      pokemon.name.toLowerCase().includes(searchPokemonField.value.toLowerCase())
    )
  }
  return pokemons.value
})

const selectPokemon = async (pokemon)=>{
  await fetch(pokemon.url)
  .then(res => res.json())
  .then(res => pokemonSelected.value = res)
  console.log(pokemon)
}

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">

          <cardPokemonSelected 
          :name="pokemonSelected?.name"
          :xp="pokemonSelected?.base_experience"
          :height="pokemonSelected?.height"
          :weight="pokemonSelected?.weight"
          :img="pokemonSelected?.sprites.other.dream_world.front_default"
          />

        </div>

        <div class="col-sm-12 col-md-6">
          <div class="card card-list">

            <div class="card-body row">

              <div class="mb-3">

                <label hidden for="searchPokemonField" class="form-label">Pesquisar...</label>

                <input v-model="searchPokemonField" type="text" class="form-control" id="searchPokemonField"
                  placeholder="Procure por um pokemon">

              </div>

              <ListPokemons v-for="pokemon in pokemonsFiltered" key="pokemon.name" :name="pokemon.name"
                :urlBaseSvg="urlBaseSvg + pokemon.url.split('/')[6] + '.svg'" 
                @click="selectPokemon(pokemon)"
                />
            </div>
          </div>
        </div>
      </div>


    </div>
  </main>
</template>

<style scoped>
.card-list{
  max-height: 440px;
  overflow-y: scroll;
  overflow-x: hidden;
}

@media (max-width:600px){
  .card-list{
  max-height: 340px;

}
}
</style>
