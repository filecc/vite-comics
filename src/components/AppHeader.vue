<template>
    <header class="row justify-content-between align-items-center h-100">
        <div class="col-2 p-2">
            <img class="img-fluid" src="../assets/img/dc-logo.png" alt="">
        </div>
        <div class="col-10 p-2 d-flex justify-content-end h-100">
            <ul class="d-flex justify-content-center gap-3 list-unstyled flex-wrap m-0 p-0 h-100">
                <li class="text-uppercase text-fg-text" v-for="link in links" :key="link.id">
                    {{ link.text }}
                </li>
            </ul>
        </div>
    </header>
</template>

<script>
import headerLinks from '../data/data.js'
export default {
    data() {
        return {
            links: headerLinks
        }
    }
}
</script>

<style lang="scss" scoped>
    * {
        font-family: 'Oswald', sans-serif;
        font-weight: 400;
    }
    img{
        max-width: 50px;
        margin: 0 auto;
    }
    li{
        font-size: 10px;
    }
</style>