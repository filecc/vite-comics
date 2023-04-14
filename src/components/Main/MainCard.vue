<template>
    <div class="cover">
        <div>
            <img class="img-fluid" :src="img" :alt="img">
        </div>

        <div>
            <p class="title-cover m-0 mt-2">{{ title }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        title: String,
        img: String,
    }
}
</script>

<style lang="scss" scoped>
.cover {
    max-width: 120px;

    img{
        width: 120px;
        height: 120px;
        object-fit: cover;
        object-position: top;
    }
}

.title-cover {
    width: fit-content;
    font-size: 10px;
}
</style>