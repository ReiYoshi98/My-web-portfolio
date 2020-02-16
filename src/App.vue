<template>
  <v-app id="inspire" v-bind:style="{'background-image': 'url(' + require('./assets/mountain.jpg') + ')'}">
    <navbar/>
    <router-view/>
  </v-app>
</template>

<script>

import Navbar from './components/Navbar'
//import Background from './components/Background'

export default {
  name: 'App',
  components: {
    Navbar
  },
  data () {
    return {
    }
  },
}
</script>

<style>
v-app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c2b2b;
  margin-top: 60px;
}

#inspire {  
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}

</style>
