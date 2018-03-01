<template> 
    <div class ='menu-container'>
        <div class ='menu'>
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
        data:function() {
            return {
                gallery:[
                    {name: 'shoreditch', subName: 'subName', desc:'desc of place...'},
                    {name: 'swimming', subName: 'subName', imgSrc: 'image2.jpg'},
                    {name: 'running', subName: 'subName', imgSrc: 'image3.jpg'},
                    {name: 'riding', subName: 'subName', imgSrc: 'image4.jpg'},
                    {name: 'flying', subName: 'subName', imgSrc: 'image5.jpg'}
                ],
                activeItemId: ''
            }
        }, components: {
            'app-gallery-item': GalleryItem
        }
    }
</script>
<style scoped>
  .menu-container {
        width:15vw;
        position: relative;
        height:100vh;
        background:#dbe6ea;
        padding-left:50px;
        padding-top:50px;
    }
</style>