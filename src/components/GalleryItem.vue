<template>
    <li 
    @mouseenter ='getItem'
    style='cursor:pointer'>{{galleryItem.name}}</li>
</template>
<script>
    import {Bus} from '../main';
    export default {
        props:['galleryItem'],
     methods: {
        getItem() {
            Bus.$emit('getItem', this.galleryItem);
            console.log(this);
        }
    }
    }
</script>