<template>

	<div class="home">
		<NavBar />
		<ListPokemon />
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
		Slider
	}
}

</script>

<style lang="scss" scoped>

.home {
	background-color: rgba(176, 176, 176, 0.333);
}


</style>