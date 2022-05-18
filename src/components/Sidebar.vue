<template>
    <div class="sidebar">
        <ul class="items-sidebar">
            <li class="item">
                <img src="../../public/img/icon-pokebolas.png" alt="">
                <span>POKEMONS</span>
            </li>

            <li class="item">
                <i class="fas fa-apple-alt"></i>
                <span>BERRIES</span>
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
        padding: 0;
        margin: 20px;

        .item {
            display: flex;
            font-weight: bold;
            font-size: 20px;
            margin: 25px 0;
            padding: 20px;
            border-radius: 15px;
            cursor: pointer;
            align-items: center;
            border: 1px solid #ff0000;

            &:hover {
                background-color: #ff0000;
                color: #fff;
            }

            img {
                width: 20px;
            }
            
            span {
                margin-left: 10px;
            }
        }
    }
}

</style>