<template>

	<div class="home">
		<NavBar />
		
		<div class="main">
			<ListPokemon />
		</div>
	</div>

</template>

<script>

import NavBar from '@/components/NavBar.vue'
import ListPokemon from '@/components/ListPokemon.vue'
import Slider from '@/components/Slider.vue'

export default {

	name: 'Home',

	components: {
		NavBar,
		ListPokemon,
		Slider,
	}
}

</script>

<style lang="scss" scoped>

.home {
	background-color: #fff5;
}


</style>