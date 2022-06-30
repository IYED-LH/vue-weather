<template>

<SearchBox @search="fetchWeather"/> 

<div class="weather-wrap"> 
  
  <div class="weather-location">
    <div class="location-name">{{weather.name}}</div>
    <div class="location-date">Wednesday, June 29, 2022</div>
  </div>


<div class="weather-box">
    <div class="temp">{{weather.temp}}<span class="cel">°C</span>
    
    <div class="weather-condition"><i class="fa-solid fa-cloud-rain"></i></div>
    </div>
      
</div>
  
</div>

    
</template>

<script>

import SearchBox from './SearchBox.vue'
const axios = require('axios').default;

export default {
  name: 'weatherBox',
  components: {
    SearchBox,
  },
    
  data() {

    return {
      api_key: '0d8595e3f9903e75e997a04c355182d4',
      api_weather: 'https://api.openweathermap.org/data/2.5/weather',
      api_geo: 'http://api.openweathermap.org/geo/1.0/direct',
      
      weather : {
        name: 'Tunisia',
        temp: '0',
        condition: '',
        
      },
      }

    },
    
  methods:{

   async fetchWeather(city){
    await  axios.get(`${this.api_weather}?q=${city}&appid=${this.api_key}`)
      .then(response => {
        this.weather = response.data;})
       }
      }
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