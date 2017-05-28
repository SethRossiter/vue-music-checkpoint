<template>
<div class="my-tunes">
    <div class="row">
        <div class ="col-xs-12" v-for="song in songs">
                <h1>My Songs</h1>
                <div class="panel panel-default"> 
                    <img :src="song.artworkUrl60" class="img-circle">
                              
                    <a href="#linkAudio"><h1>Title: {{song.trackCensoredName}}</h1></a>
                    <h3>Artist: {{song.artistName}}</h3>
                    <h3>Ablum title: {{song.collectionName}}</h3>
                    <h4>Price: {{song.collectionPrice}}</h4>
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
h1 {
    margin-top: 73px;
}

h2{
    color: white;
    text-align: right;
    text-decoration: underline white;
}
.button{
    background: green;
}
.panel{
    text-align: center;
    color: black;
    background: #c0ded9;
    margin-top: 15px;
    width: 350px;
    height: 300px;
}
.well:hover{
    background: #F9CCFF;
}
audio{
    width: 100%;
}

</style>
