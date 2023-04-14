<template>
    <header class="row justify-content-between align-items-center gx-0 container mx-auto">
        <div class="col-2 p-2">
            <img class="img-fluid" src="/img/dc-logo.png" alt="">
        </div>
        <div class="col-10 d-flex justify-content-end h-100">
            <ul class="d-flex justify-content-center gap-3 list-unstyled m-0 p-0 h-100">
                <li :id="link.id" @click="$event => handleLinkClick($event)" :class="{active: link.active}" class="text-uppercase position-relative" v-for="link in links" :key="link.id">
                    {{ link.text }}
                </li>
            </ul>
        </div>
    </header>
</template>

<script>
import headerLinks from '../data/data.js';

export default {
    data() {
        return {
            links: headerLinks
        }
    },
    methods : {
        handleLinkClick(e){
            const linkClickedId = e.target.getAttribute('id');
         
            this.links.forEach(element => {
                if (element.id == linkClickedId){
                    element.active = true
                } else {
                    element.active = false
                }
            });
        }
    }

}
</script>

<style lang="scss" scoped>
    @use '../scss/variables' as *;
    * {
        font-family: 'Oswald', sans-serif;
        font-weight: 400;
    }
    img{
        max-width: 50px;
        margin: 0 auto;
    }
    li{
        font-size: 14px;
        transition: all .3s linear;
        display: grid;
        place-items: center;
        
        &:hover{
            cursor: pointer;
            color: $fg-primary;
        }
        &.active{
            color: $fg-primary;
        }
        &:hover:after, &.active:after{
            content: '';
            width: 100%;
            height: 3px;
            background-color: $fg-primary;
            position: absolute; 
            left: 0;
            bottom: 0;
        }
    }
    
</style>