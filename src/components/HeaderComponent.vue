<template>
    <header class="container d-flex justify-content-between align-items-center p-3">
        <div class="box-logo w-50">
            <img src="../assets/img/dc-logo.png" alt="dc logo">
        </div>

        <ul v-for="link in links" :key="link.id" :id="link.id" class="list-unstyled d-flex">
            <li class="px-3">
                <a href="#" @click="setActive(link.id)" :class="{ 'active': link.active }">{{ link.title }}</a>
            </li>
        </ul>
    </header>
</template>

<script>
import {navLinks} from '../data/data.js'
    export default {
        name: 'HeaderComponent',
        data() {
            return {
                links: navLinks,
            }
        },
        methods: {
            setActive(id) {
                this.link = this.links.find(link => link.id === id);
                this.links.forEach(link => {
                    link.active = link.id === id; // Imposta mouseOver su true solo per la card corrente, altrimenti su false per le altre card
                });
                console.log(this.link.id, this.link.active)
            }
        }
    }
</script>

<style lang="scss" scoped>
header{
    height: 120px;
}

ul{ 
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
</style>