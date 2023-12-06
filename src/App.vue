<script>

import axios from 'axios';
import store from './data/store';

export default {

  name : "App",

  data(){
    return {
      message: "Hello VUEEEEEEEEEEEEEEE!"
    }
  },

  methods:{
    getApi(){
      axios.get(store.apiUrl + 'projects')
        .then(results =>{
          console.log(results.data);
        })
    }
  },

  mounted(){
    this.getApi();
  }
}


</script>

<template>
 <h1>{{ message }}</h1>
</template>

<style lang="scss">

</style>
