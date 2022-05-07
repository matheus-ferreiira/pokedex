<template>
    
    <div class="list-pokemon">
        <div v-for="(pokemon, i) in pokemons" :key="i">
            <div class="name">
                {{ pokemon.name }}
            </div>

            <div class="image">
                <img :src="pokemon.sprites.front_default"
                :alt="pokemon.name">
            </div>

            <div class="types" v-for="(type, i) in pokemon.types" :key="i">
                <div v-for="(type_name, i) in type" :key="i">
                    {{ type_name.name }}
                </div>
            </div>
        </div>
    </div>

</template>

<script>
import axios from 'axios'

export default {

    name: 'ListPokemon',

    data: () => ({

        pokemons: []

    }),

    created() {
        this.fetchPokemon();
    },

    methods: {

        fetchPokemon() {

            const getPokemonUrl = id => `https://pokeapi.co/api/v2/pokemon/${id}`

            const pokemonPromises = []

            for (let i = 1; i <= 150; i++) {
                pokemonPromises.push(fetch(getPokemonUrl(i)).then(response => response.json()))
            }

            Promise.all(pokemonPromises)
                .then(pokemons => {
                    this.pokemons = pokemons
                    console.log(this.pokemons)
                })

        }

    }

}

</script>