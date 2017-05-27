<template>
    <!-- YOU WILL PROBABLY END UP WITH SOMETHING LIKE THIS -->
<div class="container-fluid">
  <h1>SONGS</h1>
  <div class = "row">
    <itunes class="col-sm-6"></itunes>
    <Mytunes class="col-sm-6"></Mytunes>
  </div>
</div>
</template>

<script>
import Mytunes from './Mytunes'
import Itunes from './Itunes'
export default {
  name: 'home',
  data () {
    return {
      
    }
  },
  components: {
    Mytunes,
    Itunes
  }
}
</script>


<style scoped>
h1{
  text-align: center;
  color: white;
  text-shadow: 3px 3px 3px black;
  font-weight: bolder;
}



</style>
  