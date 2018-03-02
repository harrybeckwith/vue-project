<template>
    <div class='menu-container'>
        <div class='menu'>
            <div class='menu-logo'>LOGO</div>
            <ul>
                <app-gallery-item v-for='galleryItem in gallery' :galleryItem='galleryItem'> </app-gallery-item>
            </ul>
        </div>
    </div>
</template>
<script>
    import GalleryItem from './GalleryItem.vue';
    export default {
        data: function () {
            return {
                gallery: [{
                    name: 'shoreditch',
                    subName: 'subName',
                    desc: 'desc of place...1'
                },
                {
                    name: 'swimming',
                    subName: 'subName',
                    imgSrc: 'image2.jpg',
                    desc: 'desc of place...2'
                },
                {
                    name: 'running',
                    subName: 'subName',
                    imgSrc: 'image3.jpg',
                    desc: 'desc of place...3'
                },
                {
                    name: 'riding',
                    subName: 'subName',
                    imgSrc: 'image4.jpg',
                    desc: 'desc of place...4'
                },
                {
                    name: 'flying',
                    subName: 'subName',
                    imgSrc: 'image5.jpg',
                    desc: 'desc of place...5'
                }
                ]
            }
        },
        components: {
            'app-gallery-item': GalleryItem
        }, 
         created() {
            Bus.$on('slideNav', (galleryItem) => {
                this.galleryItem = galleryItem;
            });
        }
    }

</script>
<style scoped>
    .menu-container {
        width: 15vw;
        position: relative;
        height: 100vh;
        background: #dbe6ea;
        padding-left: 50px;
        padding-top: 50px;
    }
</style>