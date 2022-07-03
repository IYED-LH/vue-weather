<template>

<div class="wrapper" >

    <div class="circle">
    <i class="fa-solid fa-wind" title="wind speed"></i>
    <div class="inside-box">
    <h1>{{data.wind.speed}}<span class="percent">K/h</span></h1>
    </div>
    </div>
    


    <div class="circle">
    <i class="fa-solid fa-droplet" title="humidity"></i>
    <div class="inside-box">
    <h1>{{data.main.humidity}}<span class="percent">%</span></h1>
    </div>
    </div>

    <div class="circle">
    <i class="fa-solid fa-arrow-down-wide-short" title="pressure"></i>
    <div class="inside-box">
    <h1>{{data.main.pressure}}<span class="percent">mb</span></h1>
    </div>
    </div>
</div>

</template>


<script>

export default{
    name: 'infoBox',
    props: { 
        data: Object,
    },
   
   

}

</script>


<style scoped>

.wrapper{
 font-family: 'poppins', sans-serif;
 display: flex;
 margin: 20px;
 flex-flow: row wrap;
 justify-content: center;
 align-items: center;
 flex-direction: row;      
}
.circle{
font-size: 35px;
color: #ffffff;
text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
border : 3px solid #ffffff;
width: 150px;
height: 150px;
margin-block: 20px;
margin-inline: 30px;
padding: 12px;
padding-top: 18px;
border-radius: 50%;
justify-content: center;
align-items: center;
flex-direction: row;
background-color: rgba(226, 226, 226, 0.016);
box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
transition: 0.8s ;
}
.circle:hover{
background-color: rgba(226, 226, 226, 0.195);
transform: scale(1.1);

}

.inside-box {
    font-size: 20px;
    padding-left: 5px;
    font-weight: 500;
    border-top: #ffffff solid 1.5px;
    justify-content: center;
    align-items: center;    
}

.inside-box .percent{
font-weight: 300;
position: relative;
font-size: 15px;
bottom: 20px;

}


</style>