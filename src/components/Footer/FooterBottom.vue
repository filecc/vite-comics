<template>
    <div class="bg-fg-footer">
        <div class="container py-4 d-flex flex-column  flex-sm-row justify-content-between align-items-center ">
            <div>
                <button class="mb-3 mb-sm-0">SIGN-UP NOW!</button>
            </div>
            <div class="d-flex align-items-center gap-3">
                <h3 class="text-primary m-0">FOLLOW US</h3>
                <div class="d-flex gap-3">
                    <img src="/img/footer-facebook.png" alt="facebook">
                    <img src="/img/footer-twitter.png" alt="twitter">
                    <img src="/img/footer-youtube.png" alt="youtube">
                    <img src="/img/footer-pinterest.png" alt="pinterest">
                    <img src="/img/footer-periscope.png" alt="periscope">
                </div>
            </div>
           
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="scss" scoped>
@use '../../scss/variables' as *;
button{
    border: 1px solid $fg-primary;
    background-color: transparent;
    color: white;
    font-size: 12px;
    padding: .5rem;
    transition: all .3s linear;
    &:hover{
        background-color: $fg-primary;
    }
}
h3{
    font-family: $oswald;
    font-weight: 400;
    font-size: 12px;
}
img{
    max-width: 30px;
}
</style>