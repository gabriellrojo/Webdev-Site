<template>
  <div class="container">
    <h1>Videos</h1>
    <div class="container-videos">
      <a v-for="(video, index) in videos" :key="index" :href="video.link"><img class="thumbs" :src="video.thumb" :alt="video.link"><p>{{video.title}}</p></a>
    </div>
  </div>
</template>

<script>
import api from "../utils/api"
export default {
  name: "Videos",
  data(){
    return{
      videos: []
    }
  },
  methods: {
    getVideos(){
      api.get("https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/videos.json").then(response => this.videos = response.data)
    }
  },
  mounted(){
    this.getVideos()
  }
}
</script>



<style scoped>
  .container{
    min-height: 84vh;
    margin: 20px
  }

  h1{
    color: #FF5555;
    margin-left: 22px;
  }

  .container-videos{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  a{
    text-align: center;
  }

  .thumbs{
    width: 550px;
    margin: 50px 0
  }

  a:nth-child(3){
    margin-bottom: 50px;
  }

  @media(min-width: 720px){

    .container-videos{
      flex-direction: row;
    }
    
    a:nth-child(3){
    margin-bottom: 0;
    }
    .thumbs{
    width: 200px;
    margin: 50px 0
    }
      
  }
 
</style>
