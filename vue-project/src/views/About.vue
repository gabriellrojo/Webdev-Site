<template>
    <div class="container">   
        <h1>About</h1>
        <p>{{about.about}}</p>
        <p>{{about.about}}</p>
        <p>{{about.about}}</p>
    </div>
</template>

<script>
import api from "../utils/api"
export default {
    name:"About",
    data(){
        return {
            about:[]
        }
    },
    methods: {
        getAbout(){
            api.get("https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/about.json").then(response => this.about = response.data)
        }
        
    },
    mounted(){
        this.getAbout()
    }
}
</script>

<style scoped>
    .container{
    min-height: 84vh;
    margin: 20px
  }
    p{
        margin-left: 22px;
        margin: 40px 20px;
    }
    h1{
    color: #FF5555;
    margin: 50px 0 20px 22px ;
    }
</style>