<template>
<div class="my-tunes">
<h1>My Songs</h1>
    <div class="row">
        <div class ="col-xs-12" v-for="song in songs">
            <div class="well"> 
                <div class="art">
                    <img :src="song.artworkUrl60" class="img-circle">
                </div>               
                    <a href="#linkAudio"><h1>Title: {{song.trackCensoredName}}</h1></a>
                    <h1>Artist: {{song.artistName}}</h1>
                    <h1>Ablum title: {{song.collectionName}}</h1>
                    <h1>Price: {{song.collectionPrice}}</h1>
                    <audio controls id="linkAudio"><source :src="song.previewUrl"></audio>
                <div class="card-action">
                    <button @click="removeTrack(song)">Remove</button>
                    <button @click="promoteTrack(song)">Promote</button>
                    <button @click="demoteTrack(song)">Demote</button>
                    <span>{{song.votes}}</span>
                </div>
            </div>            
        </div>
     </div>
</div>

</template>

<script>
import MyTunesService from '../services/mytunes-service'
export default {
    name: 'my-tunes',
    data() {
        return {
            songs: MyTunesService.getTracks()
        
        }
    },
    computed: {},
    methods: {
        removeTrack(song){
            MyTunesService.removeTrack(song)
        },
        promoteTrack(song){
            MyTunesService.promoteTrack(song)
        },
        demoteTrack(song){
            MyTunesService.demoteTrack(song)
        }
    }
}
      
 
  


</script>

<style scoped>
h2{
    color: white;
    text-align: center;
    text-decoration: underline white;
}
.button{
    background: #B59AB9;
}
.well{
    text-align: center;
    color: white;
    background: #F7BDFF;
    margin: 20px;
    padding: 20px;
}
.well:hover{
    background: #F9CCFF;
}
audio{
    width: 100%;
}

</style>
