<template>
    <HeroComponent />
    <main>
        <div class="container h-100 d-flex justify-content-center align-items-center">
            <div class="section-title d-flex justify-content-center align-items-center">
                <h4 class="text-white text-uppercase px-4 py-2">current series</h4>
            </div>
            <div class="row d-flex">
                <div class="col-2 p-1 debug d-flex justify-content-center align-items-center" v-for="comic in lists" :key="comic.id" :id="comic.id">
                    <div class="card mt-3" v-if="!comic.mouseOver" @mouseover="showInfo(comic.id)" @mouseleave="hideInfo(comic.id)">
                        <div class="card-image">
                            <div class="box-image">
                                <img :src="comic.thumb" alt="comic" >
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
                    <!-- MOUSEOVER -->
                    <div class="card card-info mt-3" v-if="comic.mouseOver" @mouseover="showInfo(comic.id)" @mouseleave="hideInfo(comic.id)">
                        <div class="card-image">
                            <div class="box-image debug">
                                <img :src="comic.thumb" alt="comic">
                                <div class="info-comic d-flex flex-column p-3">
                                    <span class="text-white text-capitalize fw-semibold">series: <span class="fst-italic text-capitalize fw-normal px-1">{{ comic.series }}</span></span>
                                    <span class="text-white text-capitalize fw-semibold">price: <span class="fst-italic text-capitalize text-decoration-underline fw-normal px-1">{{ comic.price }}</span></span>
                                    <span class="text-white text-capitalize fw-semibold">type: <span class="fst-italic text-capitalize fw-normal px-1">{{ comic.type }}</span></span>
                                </div>
                            </div>
                        </div>
                        <div class="card-body">
                            <div class="name">
                                <span class="title text-uppercase fw-bold">
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
                lists: comics,
            }
        },
        methods: {
            showInfo(id) {
                this.comic = this.lists.find(comic => comic.id === id);
                this.lists.forEach(comic => {
                    comic.mouseOver = comic.id === id; // Imposta mouseOver su true solo per la card corrente, altrimenti su false per le altre card
                });
            },
            hideInfo() {
                this.lists.forEach(comic => {
                    comic.mouseOver = false; // Imposta mouseOver su false per tutte le card nell'array lists
                });
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
            cursor: pointer;
        }
        .card-info{
            position: relative;
            scale: 1.1;

            img {
                opacity: 0.3;
            }
            .info-comic{
                position: absolute;
                top: 0;
                left: 0;
            }
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
    // .debug{
    //     border: 1px solid red;
    // }
</style>