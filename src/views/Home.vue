<template>

	<div class="home">
		<NavBar />
		<div class="main">
			<Sidebar />
			<div>
				<Slider />
				<ListPokemon />
			</div>
		</div>
	</div>

</template>

<script>

import NavBar from '@/components/NavBar.vue'
import ListPokemon from '@/components/ListPokemon.vue'
import Slider from '@/components/Slider.vue'
import Sidebar from '@/components/Sidebar.vue'

export default {

	name: 'Home',

	components: {
		NavBar,
		ListPokemon,
		Slider,
		Sidebar
	}
}

</script>

<style lang="scss" scoped>

.main {
	display: flex;
}

</style>