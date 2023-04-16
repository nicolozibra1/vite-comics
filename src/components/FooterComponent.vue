<template>
    <footer class="d-flex flex-column justify-content-between">
        <div class="f-top h-100">
            <div class="container">
                <div class="row">
                    <div class="col-6 debug py-5" id="col-links">
                        <ul v-for="(link, index) in links" :key="index" class="list-unstyled d-flex flex-column flex-wrap">
                            <li class="text-uppercase fw-bold fs-5 mb-2" id="link-title">
                                {{ link.title }}
                            </li>
                            <li v-for="(item, i) in link.links" :key="i">
                                <a href="#">{{ item.text }}</a>
                            </li>
                        </ul>
                    </div>
                    <div class="col-6 debug" id="col-logo">
                        <div class="box-logo">
                            <img src="../assets/img/dc-logo-bg.png" alt="">
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="f-bottom">
            <div class="container h-100 d-flex justify-content-between align-items-center">
                <div class="sign-up">
                    <button>
                        sign-up now!
                    </button>
                </div>
                <div class="social-links h-100 d-flex align-items-center gap-3 debug">
                    <span>follow us</span>
                    <ul v-for="(link,index) in social" :key="index" class="list-unstyled debug">
                        <li class="pt-3">
                            <a href="#">
                                <img :src="'img/' + link.image" alt="">
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
import { footerLinks } from '../data/data.js';
import { socialLinks } from '../data/data.js'
    export default {
        name: 'FooterComponent',
        data() {
            return{
            links: footerLinks,
            social: socialLinks
            }
        }
    }
</script>

<style lang="scss" scoped>

    footer{
        height: calc(100vh - 450px);

        .f-top{
            background-image: url(../assets/img/footer-bg.jpg);
            overflow: hidden;

            #col-links{
                display: flex;
                flex-direction: column;
                flex-wrap: wrap;
                max-height: 440px;

                ul{
                    #link-title{
                        color: white;
                    }
                    &:hover{
                        #link-title{
                            color: #0281f9;
                        }
                    }
                }

                a{
                color: grey;
                text-decoration: none;
                text-transform: capitalize;
                font-weight: lighter;
                font-size: 0.9rem;

                    &:hover{
                        color: white;
                    }
                }
            }
            
            
            #col-logo{
                position: relative;

                .box-logo{
                    position: relative;
                    height: 100%;
                }
                img{
                    position: absolute;
                    top: -90px;
                    left: 30px;
                }
                
            }
        }
        .f-bottom{
            height: 120px;
            background-color: #303030;

            button{
                color:white;
                text-transform: uppercase;
                font-weight: bold;

                border: 2px solid #0281f9;
                padding: 12px;
                background-color: transparent;

                &:hover{
                    background-color: #0281f9;
                }
            }
            span{
                color: #0281f9;
                text-transform: uppercase;
                font-weight: bold;
                font-size: 1.2rem;
            }
            img{
                opacity: 0.25;

                &:hover{
                    opacity: 1;
                }
            }
        }
    }

</style>