<template>
<div class="weather-wrap"> 
  
  <div class="weather-location">
    <div class="location-name">Tunis, Tunisia</div>
    <div class="location-date">Wednesday, June 29, 2022</div>
  </div>


<div class="weather-box">
    <div class="temp">25<span class="cel">°C</span>
    
    <div class="weather-condition"><i class="fa-solid fa-cloud-rain"></i></div>
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
  color: #FFF;
  font-family: 'poppins', sans-serif;
  font-size: 98px;
  font-weight: 600;
  border-radius: 50%; 
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);

}
 .cel{
  position: relative;
  color: #FFF;
  font-family: 'poppins', sans-serif;
  font-size: 18px;
  font-weight: 500;
  bottom: 60px; 
}
.weather-box .weather-condition {
  color: #FFF;
  font-size: 50px;  
}

</style>