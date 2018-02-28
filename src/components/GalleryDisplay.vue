<template>
<div class ='galleryDisplay'>
  
    <div class ='galleryDisplay__text'>
         
        <h1 class ='galleryDisplay__text__title' v-if='!galleryItem'> Select item</h1>
   
        <div v-else> 
            <h1 class ='galleryDisplay__text__title'>  Name: {{galleryItem.name}} </h1>
            <img :src="'src/assets/img/' + galleryItem.name + '.jpg'">
            <p>{{galleryItem.desc}}</p>
        </div>
    
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
 <style scoped>

     .galleryDisplay {
         height:100vh;
         width:85vw;
         background:#000;
         position:relative;
     } .galleryDisplay__text {
         position: absolute;
         left:50%;
         top:50%;
         transform:translate(-50%,-50%);
         color:#fff;
        
     }
     .galleryDisplay__text__title {
   
       
     }
 </style>