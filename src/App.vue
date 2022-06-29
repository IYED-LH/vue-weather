<template>
  <main>

 <SearchBox @search="fetchWeather"/>
 <WeatherBox/>
  
  </main>
</template>

<script>

import SearchBox from './components/SearchBox.vue'
import WeatherBox from './components/WeatherBox.vue' 

export default {
  name: 'App',
  components: {
    SearchBox,
    WeatherBox,
  },
  
  
  data() {
    return {
      api_key: 'cced478c6c43ec001db0af42549b8e28',
      api_url: 'https://api.openweathermap.org/data/2.5/weather',
    }
  },
  
  methods:{
    fetchWeather(city){
    
        alert(city);
      
      
       
       }
      }
    }
    
  


</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: 'Montserrat', sans-serif;
}
#app {
  background-image: url('./assets/summerbg.jpg');
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;
}
#app.warm {
  background-image: url('./assets/winterbg.jpg');
}
main {
  min-height: 100vh;
  padding: 30px;
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.20), rgba(0, 0, 0, 0.50));
}

</style>
