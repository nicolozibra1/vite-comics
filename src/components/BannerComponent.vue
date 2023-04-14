<template>
    <div id="banner">
        <div class="container h-100">
            <ul v-for="(item, index) in items" :key="index" class="list-unstyled d-flex">
                <li>
                    <a href="#" class="d-flex justify-content-center align-items-center">
                        <img :src="'img/' + item.image" alt="">
                        <span>{{ item.title }}</span>
                    </a>
                </li>
            </ul>
        </div>
    </div>
    
</template>

<script>
import {bannerPromo} from '../data/data.js'
    export default {
        name: 'BannerComponent',
        data() {
            return {
                items: bannerPromo
            }
        },
    }
</script>

<style lang="scss" scoped>

#banner{
    background-color: #0281f9;
    height: 200px;

    .container{
        display: flex;
        justify-content: center;
        align-items: center
    }

    ul{
        max-width: 300px;
    }

    a{
        color:white;
        text-decoration: none;
        text-transform: uppercase;
        font-weight: 400;
        font-size: 0.9rem;

        img{
            width: 25%;
        }
    }
}
</style>