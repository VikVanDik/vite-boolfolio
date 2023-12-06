<script>

import axios from 'axios';
import {store} from './data/store';
import ProjectCard from './components/ProjectCard.vue';
import Loader from './components/Loader.vue';

export default {

  name : "App",

  data(){
    return {
      message: "Lista progetti",
      isLoaded: false
    }
  },

  components: {
    ProjectCard,
    Loader
  },

  methods:{
    getApi(){
      axios.get(store.apiUrl + 'projects')
        .then(results =>{
          this.isLoaded = true;
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
 <Loader v-if="!isLoaded"/>
 <div v-else>
   <h1>{{ message }}</h1>
   <ProjectCard></ProjectCard>
 </div>
</template>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
