<template>
<div class ='container flex'> 
            <app-gallery></app-gallery>
            <app-gallery-display></app-gallery-display>
</div>     
</template>
<script>
    import Gallery from './components/Gallery.vue';
    import GalleryDisplay from './components/GalleryDisplay.vue';
    export default {
        components: {
            'app-gallery': Gallery,
            'app-gallery-display': GalleryDisplay
        }
    }
</script>

<style>
    ul {
        margin: 0;
        padding:0;
    }
    body {
        padding:0;
        margin:0;
    }
    img{
        max-width:100%;
    }

</style>
<style scoped>
    .flex {
        display:flex;
    }
</style>