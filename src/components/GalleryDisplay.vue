<template>
<div>
    <p v-if='!galleryItem'> Select item</p>
    <div v-else> 
        <p> Name: {{galleryItem.name}} </p>
    </div>
 </div>
</template>
<script>
    import {Bus} from '../main';
    export default {
        data: function() {
            return {
                galleryItem: null
            }
        },
        created() {
        Bus.$on('getItem', (galleryItem)=> {
            this.galleryItem = galleryItem;
        });
    }
}

 </script>