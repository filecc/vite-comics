<template>
    <main class="grow-1">
        <div class="jumbo-div">
            <img src="/img/jumbotron.jpg" alt="jumbotron">
        </div>
        <div class="container position-relative pt-4 pb-2">
            <div class="tip">
                <p class="m-0">CURRENT SERIES</p>
            </div>
            <div class="row row-cols-2 row-cols-sm-3 row-cols-md-6">
                <div class="col p-1 d-flex justify-content-center align-items-start" v-for="item, index in data" :key="index.toString()">
                    <MainCard :title="item.series.toUpperCase()" :img="item.thumb" />
                </div>
            </div>
            <button>LOAD MORE</button>
        </div>
    </main>
</template>

<script>
import JSON from  '../../data/dc-comics.json';
import MainCard from './MainCard.vue';

export default {
    data() {
        return {
            data: JSON,
        };
    },
    components: { MainCard }
}
</script>

<style lang="scss" scoped>
@use '../../scss/variables' as *;

main {
    width: 100%;
    color: white;
}
.jumbo-div{
    max-height: 270px;
    overflow: hidden;
    min-width: 100%;
    
    img{
    min-width: 100%;
   
    max-height: 200px;
    object-fit: cover;
    object-position: top;
    }
}

.tip{
    max-width: fit-content;
    padding: .2rem .8rem;
    background-color: $fg-primary;
    font-family: $oswald;
    position: absolute;
    top: 0;
    left: 0;
    transform: translate3d(0, -50%, 0);

}
button{
    border: none;
    background-color: $fg-primary;
    color: white;
    font-family: $oswald;
    font-size: 10px;
    padding: .2rem 1.5rem;
    display: block;
    margin: 0 auto;
    transition: all .3s linear;

    &:hover{
        filter: brightness(1.2);
    }
}


</style>