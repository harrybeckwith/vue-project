<template>
    <li @mouseenter='getItem' style='cursor:pointer'>
        <h3>{{galleryItem.name}}</h3>
        <p>{{galleryItem.subName}}</p>
    </li>
</template>
<script>
    import { Bus } from '../main';
    export default {

        props: ['galleryItem'],
        methods: {
            getItem() {
                Bus.$emit('getItem', this.galleryItem);

            }
        }
    }

</script>
<style scoped>
    li {
        font-size: 20px;
        list-style: none;
    }
    
    .active {
        background: green;
    }
</style>