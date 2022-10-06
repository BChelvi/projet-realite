<template>
  <div class="home">
    <button onclick="location.href='http://www.matajava.com'" type="button">Retour à la boutique</button>           
  </div>
  <CameraComp/>
  <ArticlesComp/>
  <TroisdComp/>
</template>

<script>

import CameraComp from "../components/CameraComp.vue";
import ArticlesComp from "../components/ArticlesComp.vue";


// @ is an alias to /src


export default {
  name: 'HomeView',
  components: {
    CameraComp,
    ArticlesComp,
    
  },
  created : function(){
    const elem = document.body;
    elem.requestFullscreen();
  },
  
}
</script>

<style>
  button{
    color : white;
    background-color: #E26500;
    border-radius: 10px;
    padding: 5px;
    border :none;
    
    
  }

  .home{
    display: flex;
    justify-content: center;
    position: absolute;
    top:5%;
    right:10%;
    
  }

  body {
    background-image : url('../assets/back_indo.png');
    background-size: contain;
    
  }

</style>
