<template>
    <div class="list-pokemon">
        <div class="card-pokemon" v-for="(pokemon, i) in pokemons" :key="i">
            <!-- <div class="background"> -->
                <div class="image">
                    <img :src="pokemon.sprites.front_default"
                    :alt="pokemon.name">
                </div>
            <!-- </div> -->

            <div class="name">
                {{ pokemon.name }}
            </div>

            <div class="pokemon-id">
               Nº {{ pokemon.id }}
            </div>

            <div class="types">
                <div v-for="(type, i) in pokemon.types" :key="i">
                    <div v-for="(type_name, i) in type" :key="i">
                        <div>
                            {{ type_name.name }}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

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
            const getPokemonUrl = id => `https://pokeapi.co/api/v2/pokemon/${id}`;

            const pokemonPromises = [];

            for (let i = 1; i <= 150; i++) {
                pokemonPromises.push(fetch(getPokemonUrl(i)).then(response => response.json()));
            }

            Promise.all(pokemonPromises)
                .then(pokemons => {
                    this.pokemons = pokemons;
                });
        }
    }
}
</script>

<style lang="scss" scoped>

.list-pokemon {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
    margin: 30px;

    .card-pokemon {
        border-radius: 10px;
        box-shadow: 0px 0px 8px 0px #000;
        width: 100%;
        text-align: center;
        min-height: 300px;

        .background {
            width: 100%;
            height: 100px;
            background-color: #000;
            border-radius: 0 0 500px 500px;
        }

        .image img {
            width: 200px;
        }

        .types {
            display: flex;
            justify-content: space-around;
        }
    }
}

</style>