<template>

<SearchBox @search="fetchWeather"/> 

<div class="weather-wrap" v-if="typeof weather.main != 'undefined'"> 
  
  <div class="weather-location" >
    <div class="location-name">{{weather.name}}, {{weather.sys.country}}</div>
    <div class="location-date">{{time}}</div>

  </div>


<div class="weather-box">
    <div class="temp">{{Math.round(weather.main.temp)}}<span class="cel">°C</span>
    
    <div class="weather-condition "><i class="fa-solid fa-cloud-rain"></i></div>
    </div>
      
</div>
  
</div>


</template>

<script>
import 'animate.css';

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
      api_geo: 'https://api.openweathermap.org/geo/1.0/direct',
      api_time: 'https://api.timezonedb.com/v2.1/get-time-zone?key=N5YE68JUEOQX&format=json&by=position&lat=',
      
      weather : {},
      time:'',
    
      }
      
    },
    
  methods:{

   async fetchWeather(city){
      try{
        const response_geo = await axios.get(`${this.api_geo}?q=${city}&appid=${this.api_key}`);

        const city_name = response_geo.data[0].name;
        let lat = response_geo.data[0].lat;
        let lon = response_geo.data[0].lon;
        
        const response_weather = await axios.get(`${this.api_weather}?lat=${lat}&lon=${lon}&units=metric&appid=${this.api_key}`);
        
        this.weather = response_weather.data;
        this.weather.name = city_name;

        const response_time = await axios.get(`${this.api_time}${lat}&lng=${lon}`);
        this.time = response_time.data.formatted}

        catch(error){
          alert('City not found');
        } 
        
        this.$emit('weatherdata', this.weather);
        
      },
  },

mounted() {
    this.fetchWeather('tunis');
  },

  emits: ['weatherdata'],
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