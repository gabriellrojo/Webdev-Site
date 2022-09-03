<template>
    <div class="footer">
        <ul>
            <li v-for="(icon, index) in icons" :key="index"><a :href="icon.link"><img :src="icon.icon" :alt="icon.label" class="icon"></a></li>
        </ul>
    </div>
</template>
<script>
import api from "../utils/api"
export default {
    name: "Footer",
    data(){
        return{
            icons: []
        }
    },
    methods:{
        getIcons(){
            api.get("https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/social-links.json").then(response => this.icons = response.data)
        }
    },
    mounted(){
        this.getIcons()
    }
    
}
</script>
<style>
    .footer{
        background-color: #2B3D50;
        height: 8vh;

    }
    .footer ul {
        display: flex;
        justify-content: space-evenly;
        align-items: center;
    }
    
    .icon {
        width: 30px;
        margin-top: 12px;
    }
</style>