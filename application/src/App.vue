<template>
  <div id="app">
    <h2> Listado de documentales</h2>

    <div v-for="el in data" :key="el.id" >

      <p> Titulo {{ el.title }}</p>
      <p>{{ el.description }} </p>
      <a :href="el.video"> {{ el.video }}</a>
    </div>
  </div>
</template>

<script>

import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'

Vue.use(VueAxios, axios)
export default {
  data() {
    return {
      username: '',
      data: [],
      errorMsg: ''
    }
  },
  mounted: function (){
     const api = `http://localhost:5000/?format=json`
    
      Vue.axios.get(api).then(response => {
        this.data = response.data
      })
      
  }
}
</script>