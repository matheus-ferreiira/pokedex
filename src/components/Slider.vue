<template>
    <div class="slider">
        <img src="../../public/img/wallpaper.jpg" alt="">
    </div>
</template>

<script>

export default {
    name: 'Slider'
}

</script>

<style lang="scss" scoped>

.slider {
    width: 90%;
    margin: 0 30px;

    img {
        width: 100%;
        border-radius: 15px;
        box-shadow: 0px 0px 8px 0px #000;
    }
}

</style>