<template>
    <div class="container">
        <h1>Contato</h1>
       <ul>
           <li v-for="(contact, index) in contact" :key="index">
               <h4>{{contact.title}}</h4>
               <a :href="contact.link">{{contact.label}}</a>
           </li>
       </ul>
    </div>
</template>

<script>
import api from "../utils/api"
export default {
     name: "Contato",
     data(){
         return {
             contact: []
         }
     },
     methods: {
         getContact(){
         api.get("https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/contacts.json").then(response => this.contact = response.data)
         }
     },
     mounted(){
         this.getContact()
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
    margin: 30px 0 30px 22px

  }
  ul{
    margin-left: 22px;
    
  }
  li{
      margin: 20px 0;
  }

</style>