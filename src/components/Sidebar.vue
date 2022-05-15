<template>
    <div class="sidebar">
        <ul class="items-sidebar">
            <li class="item">
                <img src="../../public/img/icon_pokemons.png" alt="">
                POKEMONS
            </li>

            <li class="item">
                <i class="fas fa-apple-alt"></i>
                BERRIES
            </li>

            <li class="item">
                <i class="fas fa-briefcase"></i>
                <span>ITENS</span>
            </li>

            <li class="item">
                <i class="fas fa-compact-disc"></i>
                <span>ATAQUES</span>
            </li>

            <li class="item">
                <i class="fas fa-globe-africa"></i>
                <span>LOCALIZAÇÕES</span>
            </li>
        </ul>
    </div>
</template>

<script>

export default {

    name: 'Sidebar'

}

</script>

<style lang="scss" scoped>

.sidebar {
    height: 100vh;
    background-color: #fff;
    box-shadow: 0px 0px 10px 3px #000;

    .items-sidebar {
        list-style: none;
    }
}

</style>