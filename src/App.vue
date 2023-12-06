<script>

import axios from 'axios';
import {store} from './data/store';
import ProjectCard from './components/ProjectCard.vue';

export default {

  name : "App",

  data(){
    return {
      message: "Hello VUEEEEEEEEEEEEEEE!"
    }
  },

  components: {
    ProjectCard
  },

  methods:{
    getApi(){
      axios.get(store.apiUrl + 'projects')
        .then(results =>{
          store.projects = results.data.data;
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
 <ProjectCard></ProjectCard>
</template>

<style lang="scss">

</style>
