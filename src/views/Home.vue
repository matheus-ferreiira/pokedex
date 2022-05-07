<template>

	<div class="home">
		<NavBar />
		<ListPokemon />
	</div>

</template>

<script>

import NavBar from '@/components/NavBar.vue'
import ListPokemon from '@/components/ListPokemon.vue'

export default {

	name: 'Home',

	components: {
		NavBar,
		ListPokemon
	}
}

</script>
