<template>
    <header class="container">
        <div class="row justify-content-between align-items-center container mx-auto fg-navbar">
            <div class="col-2 p-2">
                <img class="img-fluid" src="/img/dc-logo.png" alt="">
            </div>
            <div class="d-none d-md-block col-10 d-flex justify-content-end h-100">
                <ul class="d-flex justify-content-center gap-3 list-unstyled m-0 p-0 h-100">
                    <li :id="link.id" @click="event => handleLinkClick(event)" :class="{ active: link.active }"
                        class="text-uppercase position-relative" v-for="link in links" :key="link.id">
                        {{ link.text }}
                    </li>
                </ul>
            </div>
            <div class="d-block d-md-hidden col-10 d-flex justify-content-end align-items-center h-100">
                <div @click="()=> open = !open" class="hm-container">
                    <div class="hamburger">
                        <div :class="{on: open}" class="hm-line one"></div>
                        <div :class="{on: open}" class="hm-line two"></div>
                        <div :class="{on: open}" class="hm-line three"></div>
                    </div>
                </div>

            </div>
        </div>
    </header>
</template>

<script>
import headerLinks from '../data/data.js';

export default {
    data() {
        return {
            links: headerLinks,
            open: false
        }
    },
    methods: {
        handleLinkClick(e) {
            const linkClickedId = e.target.getAttribute('id');

            this.links.forEach(element => {
                if (element.id == linkClickedId) {
                    element.active = true
                } else {
                    element.active = false
                }
            });
        },

    }

}
</script>

<style lang="scss" scoped>
@use '../scss/variables' as *;

* {
    font-family: $oswald;
    font-weight: 400;
}

.fg-navbar {
    height: 70px;
}

img {
    max-width: 50px;
    margin: 0 auto;
}

li {
    font-size: 14px;
    transition: all .3s linear;
    display: grid;
    place-items: center;

    &:hover {
        cursor: pointer;
        color: $fg-primary;
    }

    &.active {
        color: $fg-primary;
    }

    &:hover:after,
    &.active:after {
        content: '';
        width: 100%;
        height: 3px;
        background-color: $fg-primary;
        position: absolute;
        left: 0;
        bottom: 0;
    }
}

/* HAMBURGER */
.hm-container {
    position: relative;
    width: $width;
    height: $width;
    display: flex;
    justify-content: center;
    align-items: center;
}

.hamburger {
    width: calc($width / 2);
    height: calc($width / 3);
    display: block;
    cursor: pointer;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}

.hm-line {
    background-color: $line-color;
    width: calc($width * .5);
    height: calc($width * .04);
    position: relative;
    transition: 0.3s ease all;
    border-radius: 5px;
}

.hm-line.one.on {
    position: absolute;
    transform: rotateZ(45deg);

}

.hm-line.two.on {
    width: 0;
}

.hm-line.three.on {
    position: absolute;
    transform: rotateZ(-45deg);

}
</style>