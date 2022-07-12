<template>
	<nav class="navbar">
		<div class="search">
			<i class="fas fa-search"></i>
			<input type="text" placeholder="Search Pokemons">
		</div>
	</nav>
</template>

<script>

export default {

	name: 'NavBar',
	
}

</script>

<style lang="scss" scoped>

.navbar {
	height: 350px;
    display: grid;
    text-align: center;
    align-items: center;
	justify-items: center;
    box-shadow: 0px 0px 10px 3px #000;
    background-color: #ff0000;

	.search {
		display: grid;
		align-items: center;
		background-color: #fff;
		width: 70%;
		border-radius: 20px;
		grid-template-columns: 0fr 1fr 0fr;
		
		i {
			margin-left: 30px;
		}

		input {
			width: 100%;
			height: 50px;
			border: none;
			outline: none;
			border-radius: 20px;
		}
	}
	
	.img {
		img {
			width: 150px;
		}
	}
}

</style>