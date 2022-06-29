<template>
  <main>

 <SearchBox/>
  
  </main>
</template>

<script>

import SearchBox from './components/SearchBox.vue' 

export default {
  name: 'App',
  components: {
    SearchBox
  },
  
  
  data() {
    return {
      api_key: 'cced478c6c43ec001db0af42549b8e28'
    }
  }
  
}

</script>

<style>
@import url('http://fonts.cdnfonts.com/css/montserrat');

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: 'montserrat', sans-serif;
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

.location-box .location {
  color: #FFF;
  font-size: 32px;
  font-weight: 500;
  text-align: center;
  text-shadow: 1px 3px rgba(0, 0, 0, 0.25);
}
.location-box .date {
  color: #FFF;
  font-size: 20px;
  font-weight: 300;
  font-style: italic;
  text-align: center;
}
.weather-box {
  text-align: center;
}
.weather-box .temp {
  display: inline-block;
  padding: 10px 25px;
  color: #FFF;
  font-size: 102px;
  font-weight: 900;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
  background-color:rgba(255, 255, 255, 0.25);
  border-radius: 16px;
  margin: 30px 0px;
  box-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}
.weather-box .weather {
  color: #FFF;
  font-size: 48px;
  font-weight: 700;
  font-style: italic;
  text-shadow: 3px 6px rgba(0, 0, 0, 0.25);
}

</style>
