<template>

    <div>
        <p v-if="!galleryItem">Please select a Server</p>

        <div class='galleryDisplay' v-else>



            <div class='galleryDisplay__text'>



                <div>
                    <h1 class='galleryDisplay__text__title'> Name: {{galleryItem.name}} </h1>

                    <p>{{galleryItem.desc}}</p>
                </div>

            </div>
            <button @click="toggleNav">Know more</button>
            <div class='galleryDisplay__sideMenu' :class='{isSlide}'>
                <p>{{galleryItem.desc}}</p>
            </div>

        </div>


    </div>

</template>
<script>
    import { Bus } from '../main';
    export default {
        data: function () {
            return {
                galleryItem: null,
                isSlide: false
            }
        },
        created() {
            Bus.$on('getItem', (galleryItem) => {
                this.galleryItem = galleryItem;
            });
        },
        methods: {
            toggleNav() {
                const menu = document.querySelector('.menu-container');
                menu.classList.toggle('slide-nav');
                this.isSlide = !this.isSlide;
            }
        }
    }

</script>
<style>
    .galleryDisplay {
        height: 100vh;
        width: 85vw;
        background: #000;
        position: relative;
    }
    
    .galleryDisplay__text {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        color: #fff;
    }
    
    .galleryDisplay__sideMenu {
        position: absolute;
        background: blue;
        right: -20%;
        top: 0;
        bottom: 0;
        height: 100vh;
        width: 20%;
        transition: 1s all;
    }
    
    .isSlide {
        background: green;
        right: 0;
    }
    
    .slide-nav {
        background: green !important;
    }
</style>