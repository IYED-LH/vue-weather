<template>

<div :class="typeof weather.main != 'undefined' && weather.main.temp <= 20 ? 'warm' : '' ">

  <main>
  
 <WeatherBox @weatherdata="getWeatherData"/>
  
  </main>

  </div>

</template>

<script>


import WeatherBox from './components/WeatherBox.vue' 

export default {
  name: 'App',
  components: {
    WeatherBox,
  }, 
  data() {
    return {
      weather: {},
    }
  },
  methods: {
    getWeatherData(weather) {
      this.weather = weather;
    }
  },
  
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
