<template>
<div>
  <div v-for="home in homes" :key="home.objectID" style="float: left; margin: 20px">
    <nuxt-link :to="`/home/${home.objectID}`"><home-card :home="home"/></nuxt-link>
  </div>
</div>
</template>
<script>

import homes from '~/data/homes'
import HomeCard from '../components/HomeCard.vue'
// deduce import + define components

export default {
  components: { HomeCard },
  head(){
    return {
      title: 'Homepage',
      meta: [{
        name: 'description',
        content: 'This is a homepage!',
        hid: 'description'
      }]
    }
  },

  data() {
    return{
      homes: homes.slice(0,3)
    }
  },
}
</script>
