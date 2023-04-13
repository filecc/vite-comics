
import FooterTop from './FooterTop.vue';

<template>
    <footer>
        <FooterTop />
        <FooterMiddle />
        <FooterBottom />
    </footer>
</template>

<script>
import { footerImg } from '../data/data';
import FooterTop from './FooterTop.vue';
import FooterMiddle from './FooterMiddle.vue'
import FooterBottom from './FooterBottom.vue';
    export default {
        components: {
    FooterTop,
    FooterMiddle,
    FooterBottom
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