<template>
  <div>
    <div style="display:flex;">
      <img v-for="image in home.images" :key="image" :src="image" height="150" width="200"/>
    </div>
    {{ home.title }}<br/>
    ${{ home.pricePerNight }} / night <br/>
    {{ home.location.address }}, {{ home.location.city }}, {{ home.location.state }}, {{ home.location.country }}<br/>
    {{ home.reviewValue }}<br/>
    {{ home.guests }} guests, {{ home.bedrooms }} bedrooms, {{ home.beds }} beds, {{ home.bathrooms }} bath<br/>

  </div>
</template>
<script>
import homes from '~/data/homes'
export default {
  data(){
    return{
      home: {},
    }
  },
  created() {
    const home = homes.find((home) => home.objectID == this.$route.params.id)
    this.home = home
  }
}
</script>