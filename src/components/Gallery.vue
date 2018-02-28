<template> 
    <div>
        <app-gallery-item v-for='galleryItem in gallery' :galleryItem='galleryItem'> </app-gallery-item>
    </div>
</template>
<script>
    import GalleryItem from './GalleryItem.vue';
    export default {
        data:function() {
            return {
                gallery:[
                    {name: 'snorkelling', imgSrc: 'image1.jpg'},
                    {name: 'swimming', imgSrc: 'image2.jpg'},
                    {name: 'running', imgSrc: 'image3.jpg'},
                    {name: 'riding', imgSrc: 'image4.jpg'},
                    {name: 'flying', imgSrc: 'image5.jpg'}
                ]
            }
        }, components: {
            'app-gallery-item': GalleryItem
        }
    }
</script>