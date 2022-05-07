<template>
    
    <div>
        {{ pokemons }}
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
        this.loadListPokemon();
    },

    methods: {

        loadListPokemon(limit = 50, offset = 0) {

            axios
                .get(`https://pokeapi.co/api/v2/pokemon?limit=${limit}&offset=${offset}`)
                .then((response) => {
                    this.pokemons = response.data;
                })
                .catch(() => {

                });

        }

    }

}

</script>