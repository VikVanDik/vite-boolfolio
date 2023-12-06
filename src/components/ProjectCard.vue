<script>

import {store} from '../data/store';

export default {

  name : "ProjectCard",

  data(){
    return {
      store
    }
  },
  mounted(){
    console.log(store.projects)
  }
}


</script>

<template>
  <ul>
    <li v-for="project in store.projects" :key="project.id">{{ project.name }}</li>
  </ul>
</template>

<style lang="scss">

</style>