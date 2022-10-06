<template>
    <div class="caroussel">
        <span style="color:white">〈</span>
        <div class="article">
            <img src="../assets/bracelet.jpg">
        </div>
        <span style="color:white">〉</span>

    </div>
</template>

<script>
    export default{
        name:'ArticlesComp',
       
    }
    
</script>

<style>
    .article{
        width: 100px;
        height: 100px;
              
        
    }

    .caroussel{
        display :flex;
        flex-direction: row;
        justify-content: space-around;
        width: 100%;
        position : absolute;
        bottom : 15%;
        align-items: center;
    }

    img{
        object-fit: contain;
        width: 100%;
        height: 100%;
        border-radius: 10px; 
    }
</style>