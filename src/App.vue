<template>
    <div class="container">
        <h1> Live Life London </h1>
        <div class ='row'>
            <div class ='col-md-3'>
            <app-gallery></app-gallery>
        </div>
        <div class ='col-md-9'>
                <app-gallery-display></app-gallery-display>
        </div>
        </div>
       
        
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

</style>
