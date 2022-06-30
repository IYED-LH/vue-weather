<template>

<div >
  <input class="search-bar" type="text" placeholder="search..."
  v-model="city" @keyup.enter="$emit('search',city)">
  
</div>
  
</template>

<script>
export default {
  name: 'SearchBox',
  
  
  
  data() {
    return {
      city: '',
     
    }
  },
  emits: ['search'],
  

}
</script>

<style scoped>

.search-bar {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 75%;
  padding: 15px;
  margin-bottom: 30px;
  color: #313131;
  font-size: 20px;
  appearance: none;
  border:none;
  outline: none;
  background: none;
  box-shadow: 0px 0px 8px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.5);
  border-radius: 0px 16px 0px 16px;
  transition: 0.4s;
}
.search-bar:focus {
  box-shadow: 0px 0px 25px rgba(0, 0, 0, 0.25);
  background-color: rgba(255, 255, 255, 0.75);
  border-radius: 25px 25px 25px 25px;
}

</style>