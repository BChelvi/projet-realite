<template>
    <div class="camera">
        <video autoplay class="feed"></video>
        <div class="bouton">
            <button class="snap" v-on:click='startCamera()'>Start</button>           
            <button class="snap" v-on:click='closeCamera()'>Couper</button>
        </div>        
    </div>
</template>

<script>   
    export default{
        name:'SetCamera',
        data(){
            return{
                videoPlayer : null
            }
        },
        methods :{
            startCamera(){
            if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia){
                        let constraints = {
                                video:{
                                    width: 1280,
                                    height: 720 ,  
                                    facingMode: {
                                        exact: 'environment'
                                    },
                                    aspectRatio : 1/1,
                                    
                                }
                            };
                        navigator.mediaDevices.getUserMedia(constraints).then(stream=>{
                    

                            this.videoPlayer = document.querySelector("video");
                            this.videoPlayer.srcObject = stream;
                            this.videoPlayer.play();
                            
                            
                        });
                }
                else {
                alert("Cannot get Media Devices")
                }
            },
            closeCamera(){   
                    
                this.videoPlayer.pause();
                this.videoPlayer.src="";
                const stream = this.videoPlayer.srcObject;
                const tracks = stream.getTracks();
                tracks.forEach(function (track) {
                track.stop();
                });
                this.videoPlayer.srcObject = null;
            },
           
          
        
        },
        
       
       
    }
</script>

<style lang="css" scoped>
    .camera {
        width:100%;
        
        height: 90vh; 
       
        
    }
    .feed {
        width: 100%;
        max-width: 1280px;
        height: 100%;
        background-color:  #171717;
        box-shadow : 6px 6px 12px 0 rgba(0, 0, 0, 0.35);
        }
    .bouton{
        display:flex;
        justify-content: space-around;
        position: absolute;
        bottom: 5%;
        width: 100%;
        
    }
    .snap{
        width: 75px;
        height: 30px;
        border: none;
        background-color: #E26500;
        outline :none;
        cursor: pointer;
        color : white;
        z-index: 1000;
        
    }
    .snap:hover{
        background-color: white;
        color : #E26500;

    }

    .snap:active{
        background-color: white;
        color : #E26500;
    }


</style>