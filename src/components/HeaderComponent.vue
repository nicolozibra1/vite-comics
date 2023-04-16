<template>
    <header class="container d-flex justify-content-between align-items-center p-3">
        <div class="container-logo w-50 debug">
            <div class="box-logo debug">
                <img src="../assets/img/dc-logo.png" alt="dc logo" class="debug">
            </div>
        </div>
        <a href="#" class="hamburger fs-4" @click="openMenu" v-if="!open"><i class="fa-solid fa-bars"></i></a>
        <a href="#" class="cross fs-2" @click="closeMenu" v-if="close"><i class="fa-solid fa-xmark"></i></a>
        <ul v-for="link in links" :key="link.id" :id="link.id" class="navbar list-unstyled">
            <li class="px-3">
                <a href="#" @click="setActive(link.id)" :class="{ 'active': link.active }">{{ link.title }}</a>
            </li>
        </ul>
    </header>
    <div class="v-menu" v-if="open">
        <ul v-for="link in links" :key="link.id" :id="link.id" class="list-unstyled mb-2">
            <li>
                <a href="#" @click="setActive(link.id)" :class="{ 'active': link.active }">{{ link.title }}</a>
            </li>
        </ul>
    </div>
</template>

<script>
import {navLinks} from '../data/data.js'
    export default {
        name: 'HeaderComponent',
        data() {
            return {
                links: navLinks,
                open: false,
                close: false
            }
        },
        methods: {
            setActive(id) {
                this.link = this.links.find(link => link.id === id);
                this.links.forEach(link => {
                    link.active = link.id === id; // Imposta active su true solo per la selezione corrente, altrimenti su false per tutte le altre voci
                });
                console.log(this.link.id, this.link.active)
            },
            openMenu() {
                this.open = true;
                this.close = true;
            },
            closeMenu() {
                this.close = false;
                this.open = false;
            }
        }
    }
</script>

<style lang="scss" scoped>
header{
    height: 120px;
}
.box-logo{
    height: 80px;
    width: 80px;

    img{
        width: 100%;
        height: 100%;
    }
}
ul{ 
    display: flex;

    li a{
        text-decoration: none;
        color: black;
        text-transform: uppercase;
        font-family: 'Roboto','sans-serif';
        font-weight: 600;
        font-size: 0.9rem;
        cursor: pointer;

        &:hover {
            border-bottom: 3px solid #0281f9;
        }
        &.active{
            border-bottom: 3px solid #0281f9;
        }
    }
}
// .debug{
//     border: 1px solid red;
// }
@media screen and (max-width: 992px) {
    header{
        height: 100px;
    }
    .navbar{
        display: none;
    }
    .v-menu{
        position: absolute;
        top: 100px;
        left: 0;
        width: 100%;
        height: 400px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-color: white;
    }
    .box-logo{
        width: 75px;
        height: 75px;
    }
}
@media screen and (min-width: 992px) {
    .hamburger{
        display: none;
    }
    .v-menu{
        display: none;
    }
}
</style>