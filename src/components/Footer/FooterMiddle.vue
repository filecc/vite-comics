<template>
    <div class="py-4 bg overflow-hidden">
        <div class="container">
            <div class="row position-relative justify-content-center justify-content-sm-start">
                <div class="col">
                <h2>{{ links[0].title}}</h2>
                <ul class="list-unstyled">
                    <li :key="link.text" v-for="link in links[0].links">{{ link.text }}</li>
                </ul>
                <h2>{{ links[1].title}}</h2>
                <ul class="list-unstyled">
                    <li :key="link.text" v-for="link in links[1].links">{{ link.text }}</li>
                </ul>
            </div>
            <div class="col">
                <h2>{{ links[2].title}}</h2>
                <ul class="list-unstyled">
                    <li :key="link.text" v-for="link in links[2].links">{{ link.text }}</li>
                </ul>
            </div>
            <div class="col">
                <h2>{{ links[3].title}}</h2>
                <ul class="list-unstyled">
                    <li :key="link.text" v-for="link in links[3].links">{{ link.text }}</li>
                </ul>
            </div>
            <div class="col gx-0">
                <img class="img-fluid logo-bg" src="/img/dc-logo-bg.png" alt="">
            </div>
            </div>
        </div>
    </div>
</template>

<script>
import { footerLinks } from '../../data/data';
    export default {
        data(){
            return {
                links: footerLinks
            }
        }
    }
</script>

<style lang="scss" scoped>
 @use '../../scss/variables' as *;
.bg{
    background: url('/img/footer-bg.jpg');
    background-repeat: no-repeat;
    background-size: cover;
}
h2{
    color: white;
    text-transform: uppercase;
    font-size: 18px;
    font-family: $oswald;
    font-weight: 400;
    max-width: fit-content;
}
li{
    color: #909090;
    text-transform: capitalize;
    font-size: 12px;
    position: relative;
    z-index: 1000;

    &:hover{
        color: white;
        cursor: pointer;
    }
}
ul, .col{
    max-width: fit-content;
}
.logo-bg{
    max-width: 450px;
    position: absolute;
    right: 0;
    top: -50%;
    z-index: 0;
}
</style>