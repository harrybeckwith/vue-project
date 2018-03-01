<template>

<div class ='galleryDisplay'>
  


    <div class ='galleryDisplay__text'>
         
        <p v-if='!galleryItem'> asasa</p>
   
        <div v-else> 
            <h1 class ='galleryDisplay__text__title'>  Name: {{galleryItem.name}} </h1>
          
            <p>{{galleryItem.desc}}</p>
        </div>
    
    </div>
    <button>Know more</button>
    <div class ='galleryDisplay__sideMenu'>
        
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
         color:#000;
        
     }
         
     .galleryDisplay__sideMenu {
            position: absolute;
            background:blue;
            right:0;
            top:0;
            bottom:0;
            height:100vh;
            width:20%;
     }
 </style>