<template>
    <div class="list-pokemon">
        <div class="card-pokemon" v-for="(pokemon, i) in pokemons" :key="i">
            <div class="background">
                <div class="pokemon-id">
                    Nº {{ pokemon.id }}
                </div>
            </div>

            <div class="image">
                <img :src="pokemon.sprites.other.dream_world.front_default"
                :alt="pokemon.name">
            </div>

            <div class="info-pokemon">
                <div class="name">
                    {{ pokemon.name }}
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
    </div>
</template>

<script>

export default {
    name: 'ListPokemon',

    data: () => ({
        pokemons: [],

        typeColor : {
            bug: "#26de81",
            dragon: "#ffeaa7",
            electric: "#fed330",
            fairy: "#ff0069",
            fighting: "#30336b",
            fire: "#f0932b",
            flying: "#81ecec",
            grass: "#00b894",
            ground: "#efb549",
            ghost: "#a55eea",
            ice: "#74b9ff",
            normal: "#95afc0",
            poison: "#6c5ce7",
            psychic: "#a29bfe",
            rock: "#2d3436",
            water: "#0190ff"
        }
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

                    const themeColor = this.typeColor[this.pokemons[0].types[0].type.name];
                });
        }
    }
}
</script>

<style lang="scss" scoped>

.list-pokemon {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    margin: 30px;

    .card-pokemon {
        border-radius: 10px;
        box-shadow: 0px 0px 8px 0px #000;
        width: 100%;
        text-align: center;
        min-height: 300px;

        .background {
                width: 100%;
                background: blue;
                height: 170px;
                padding-top: 15px;
                border-radius: 10px 10px 200px 200px;

            .pokemon-id {
                width: 80px;
                background-color: #fff;
                text-align: center;
                padding: 8px 0;
                border-radius: 30px;
                margin-right: 15px;
                margin-left: auto;
                font-weight: bold;
            }
        }

        .info-pokemon {
            margin: 20px;
            
            .name {
                font-size: 20px;
                font-weight: bold;
                margin: 20px;
            }

            .types {
                display: flex;
                justify-content: space-around;
            }
        }

        .image  {
            margin-top: -150px;

            img {
                display: block;
                width: 180px;
                height: 200px;
                margin: 20px auto;
            }
        }
    }
}

</style>