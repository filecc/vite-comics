<template>
    <header class="row justify-content-between align-items-center h-100 gx-0">
        <div class="col-2 p-2">
            <img class="img-fluid" src="../assets/img/dc-logo.png" alt="">
        </div>
        <div class="col-10 p-2 d-flex justify-content-end h-100">
            <ul class="d-flex justify-content-center gap-3 list-unstyled flex-wrap m-0 p-0 h-100">
                <li :id="link.id" @click="$event => handleLinkClick($event)" :class="{active: link.active}" class="text-uppercase" v-for="link in links" :key="link.id">
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
        font-size: 10px;
        
        &:hover{
            cursor: pointer;
            color: $fg-primary;
        }
    }
    
</style>