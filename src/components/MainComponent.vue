<template>
    <HeroComponent />
    <main>
        <div class="container h-100 d-flex justify-content-center align-items-center">
            <div class="section-title d-flex justify-content-center align-items-center">
                <h4 class="text-white text-uppercase px-4 py-2">current series</h4>
            </div>
            <div class="row d-flex">
                <div class="col-2 p-1" v-for="(comic, index) in lists" :key="index">
                    <div class="card mt-3">
                        <div class="card-image">
                            <div class="box-image">
                                <img :src="comic.thumb" alt="comic">
                            </div>
                        </div>
                        <div class="card-body">
                            <div class="name">
                                <span class="title text-uppercase">
                                    {{ comic.series }}
                                </span>
                            </div>
                        </div>    
                    </div>
                </div>
            </div>
        </div>
        <div class="container d-flex justify-content-center align-items-center">
            <button class="px-5 py-2">
                load more
            </button>
        </div>
        
    </main>
</template>

<script>
import { comics } from '../data/data.js'
import HeroComponent from './HeroComponent.vue';
    export default {
        name: 'MainComponent',
        components: {
            HeroComponent
        },
        data() {
            return {
                lists: comics
            }
        }
    }
</script>

<style lang="scss" scoped>
    main{
        background-color: #1c1c1c;
        padding-bottom: 40px;
        padding-top: 55px;
        position: relative;

        h4{
            background-color: #0281f9;
            position: absolute;
            top:-20px;
            left: 300px;
            font-weight: 600;
        }
        .card{
            width: 95%;
            border: none;
            background-color: transparent;
        }
        .box-image{
            height: 180px;
            width: 90%;
            margin: auto;

            img{
                height: 100%;
                width: 100%;
                object-fit: cover;
                object-position: top;
            }
        }
        .title{
            font-size: 0.8rem;
            color: white;
            font-weight: 400;
        }
        button{
            color: white;
            text-transform: uppercase;
            background-color: #0281f9;
            font-weight: 600;
            font-size: 0.9rem;


        }
    }
</style>