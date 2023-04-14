<template>
    <header class="container d-flex justify-content-between align-items-center p-3">
        <div class="box-logo w-50">
            <img src="../assets/img/dc-logo.png" alt="dc logo">
        </div>

        <ul v-for="(link, index) in links" :key="index" class="list-unstyled d-flex">
            <li class="px-3">
                <a href="#">{{ link.title }}</a>
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
                links: navLinks
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
    }
}
</style>