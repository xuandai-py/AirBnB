<template>
  <div>
    <div style="display: flex;">
      <img v-for="image in home.images" :key="image" :src="image" width="200" height="150" alt="images"/> <br/>
    </div>
    {{home.title}}<br/>
    ${{home.pricePerNight}}/night <br/>
    <img src="/images/marker.svg" width="20px" height="20px" alt="marker.svg" />{{home.location.address}} {{home.location.city}} {{home.location.state}} {{home.location.country}}<br/>
    <img src="/images/star.svg" width="20px" height="20px" alt="star.svg" />{{home.reviewValue}}<br/>
    {{home.guests}} guests, {{home.bedrooms}} rooms, {{home.beds}} beds, {{home.bathrooms}} baths
  </div>
</template>

<script>
import homes from '~/data/homes'

export default({
  head(){
    return {
      title: this.home.title
    }
  },
  data(){
    return {
      home: {}
  }
  },
  created(){
    const home = homes.find((home) => home.objectID == this.$route.params.id)
    this.home = home
  }
})
</script>