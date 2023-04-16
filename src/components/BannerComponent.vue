<template>
    <div id="banner">
        <div class="container h-100">
            <ul v-for="(item, index) in items" :key="index" class="list-unstyled debug">
                <li>
                    <a href="#" class="d-flex justify-content-s align-items-center debug">
                        <div class="box-logo debug">
                            <img :src="'img/' + item.image" alt="logo" class="">
                        </div>
                        <span class="ps-4">{{ item.title }}</span>
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

    .container{
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 50px;
    }

    ul{
        width: 300px;
    }

    a{
        color:white;
        text-decoration: none;
        text-transform: uppercase;
        font-weight: 400;
        font-size: 0.9rem;

        .box-logo{
            width: 100px;
            height:60px;
        }
        img{
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
    }
}
@media screen and (max-width: 992px) {
    .container{
        flex-direction: column;
    }
}
</style>