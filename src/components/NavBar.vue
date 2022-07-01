<template>
	<nav class="navbar">
		<div class="img">
			<img src="../../public/img/logo.png" alt="">
		</div>

		<div class="search">
			<input type="text">
			<button></button>
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
    grid-template-columns: 20% 80%;
    text-align: center;
    align-items: center;
    box-shadow: 0px 0px 10px 3px #000;
    background-color: #ff0000;

	.search {

		input {
			width: 80%;
		}
	}
	
	.img {
		img {
			width: 150px;
		}
	}
}

</style>