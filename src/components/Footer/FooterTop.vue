<template>
     <div class="bg-primary">
        <div class="container py-4">
           <div class="row justify-content-center gap-2 flex-column flex-md-row">
            <div v-for="image in images" class="col d-flex justify-content-center align-items-center gap-1" :key="image.id">
                <div class="p-1">
                    <img class="img-fluid" :src="'/img/'+image.src" :alt="image.alt">
                </div>
                <p class="m-0">{{ image.description }}</p>
            </div>
           </div>
        </div>
    </div>
</template>

<script>
import { footerImg } from '../../data/data';
    export default {
        data() {
            return {
                images: footerImg,
            }
        }
    }
</script>

<style lang="scss" scoped>
    @use '../../scss/variables' as *;
    p{
        font-family: $oswald;
        font-weight: 200;
        color: white;
        font-size: 12px;
        text-transform: uppercase;
    }
    img{
        min-width: 50px;
        max-height: 40px;
        object-fit: contain;
    }
    
</style>