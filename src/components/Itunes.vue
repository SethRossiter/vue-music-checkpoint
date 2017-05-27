<template>
  <div class="itunes">
    <form  class="form-inline" @submit.prevent="getMusic">
      <div class="form-group">
        <input type="text" class="form-control" v-model="artist" name= "artist">
        <button type="submit" class="btn btn-primary btn-lg">Search for Music</button>
      </div>
    </form>
    <div class="row">
      <div class='col-xs-4 text-center' v-for="song in songs"> 
        <div class="panel panel-default"> 
          <img :src="song.artworkUrl60" class="img-circle"> 
          <h3>Artist: {{song.artistName}}</h3>
          <h4>Ablum title: {{song.collectionName}}</h4>
          <h6>Price: {{song.collectionPrice}}</h6>
          <a href="#linkAudio">Title: {{song.trackCensoredName}}</a>
          <audio controls id="linkAudio"><source :src="song.previewUrl"></audio>
        </div>
          <button class="btn lg" @click="addTunes(song)">Add</button>
      </div>
    </div>
  </div>
 
</template>
   
          
<script>
import ItunesService from '../services/itunes-service'
import MyTunesService from '../services/mytunes-service'
export default {
  name: 'itunes',
  data () {
    return {
      artist: '',
      songs: []
      }
    },
    computed: {},
    methods: {
      getMusic(){
        ItunesService.getMusicByArtist(this.artist).then(res=>{
        let resObj = JSON.parse(res)
        this.songs = resObj.results
      })
    },
    addTunes(song){
      MyTunesService.addTrack(song)
    }
  }
}
</script>


<style scoped>
.form{
    padding: 20px;
    text-align: center;
}
.img-circle{
  width: 75%;
  padding-top: 20px;
}

.button{
    background: ;
    font-size: 18px;
    text-align: center;
   
}
.panel{
    text-align: center;
    color: black;
    background: ghostwhite;
    margin: 10px;
}
audio{
    width: 100%;
}
.well:hover{
    background: #F9CCFF;
}

</style>
                
                 
              
                
             
            
                

