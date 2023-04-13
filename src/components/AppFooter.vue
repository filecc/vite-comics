
import FooterTop from './FooterTop.vue';

<template>
    <footer class="py-4 bg-primary">
        <FooterTop />
    </footer>
</template>

<script>
import { footerImg } from '../data/data';
import FooterTop from './FooterTop.vue';
    export default {
        components: {
            FooterTop,
        },
        data() {
            return {
                images: footerImg,
            }
        }
    }
</script>

<style lang="scss" scoped>
    @use '../scss/variables' as *;
    

</style>