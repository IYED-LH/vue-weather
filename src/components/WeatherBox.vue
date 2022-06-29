<template>
<div class="weather-wrap"> 
  
  <div class="weather-location">
    <div class="location-name">Tunis, Tunisia</div>
    <div class="location-date">Wednesday, June 29, 2022</div>
  </div>


<div class="weather-box">
    <div class="temp">25<span class="cel">°C</span>
    
    <div class="weather"> Partly Cloudy </div>
    </div>
      
</div>
  
</div>

    
</template>

<script>
export default {
  name: 'SearchBox',
  
}
</script>

<style scoped> 

.location-name {
  color: #FFF;
  font-size: 48px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}
.location-date {
  color: #FFF;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}
.weather-box {
  text-align: center;
  
  
}
.temp {
  display: inline-block;
  color: #FFF;
  padding: 50px;
  
  font-size: 98px;
  font-weight: 700;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color:rgba(255, 255, 255, 0.25);
  height: 300px;
  width: 300px;
  border-radius: 50%;
  margin: 30px 0px;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.temp .cel{
  position: relative;
  font-size: 60px;
  font-weight: 700;
  bottom: 50px;
  
}
.weather-box .weather {
  color: #FFF;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}



</style>