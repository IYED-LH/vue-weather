<template>

<SearchBox @search="fetchWeather"/> 

<div class="weather-wrap" v-if="typeof weather.main != 'undefined'"> 
  
  <div class="weather-location" >
    <div class="location-name">{{weather.name}}, {{weather.sys.country}}</div>

    <div class="location-date">{{date}}, {{time}}</div>
    
    

  </div>


<div class="weather-box" >
    <div class="temp">{{Math.round(weather.main.temp)}}<span class="cel">°C</span>
    
    <div class="weather-condition" v-if="weather.weather[0].main == 'Clouds'"><i class="fa-solid fa-cloud"></i></div>
    <div class="weather-condition" v-else><i class="fa-solid fa-sun"></i></div>
    
      
</div>

  <infoBox/>
  
</div>

</div>


</template>

<script>

import SearchBox from './SearchBox.vue'
import InfoBox from './InfoBox.vue'
const axios = require('axios').default;

export default {
  name: 'weatherBox',
  components: {
    SearchBox,
    InfoBox,
    
  },
    
  data() {

    return {
      api_key: '0d8595e3f9903e75e997a04c355182d4',
      api_weather: 'https://api.openweathermap.org/data/2.5/weather',
      api_geo: 'https://api.openweathermap.org/geo/1.0/direct',
      api_time: 'https://api.timezonedb.com/v2.1/get-time-zone?key=N5YE68JUEOQX&format=json&by=position&lat=',
      
      weather : {},
      date:'',
      time:'',
      
    
      }
      
    },
    
  methods:{

  // Fetching the weather data from the API 
   async fetchWeather(city){
      try{
        const response_geo = await axios.get(`${this.api_geo}?q=${city}&appid=${this.api_key}`);

        const city_name = response_geo.data[0].name;
        let lat = response_geo.data[0].lat;
        let lon = response_geo.data[0].lon;
        
        const response_weather = await axios.get(`${this.api_weather}?lat=${lat}&lon=${lon}&units=metric&appid=${this.api_key}`);
        
        this.weather = response_weather.data;
        this.weather.name = city_name;

        
         // Getting the current time from the timeapi.io API.
         const response_time = await axios.get(`https://timeapi.io/api/Time/current/coordinate?latitude=${lat}&longitude=${lon}`);
         this.time = response_time.data.time;

         
         // Getting the current date and time and assigning it to the variable `date`
         const d = new Date();
         let months = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];
         let days = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
         let day = days[d.getDay()];
         let date = d.getDate();
         let month = months[d.getMonth()];
         let year = d.getFullYear();
         this.date = `${day}, ${date} ${month} ${year}`;

          }

        catch(error){
          alert('City not found');}

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