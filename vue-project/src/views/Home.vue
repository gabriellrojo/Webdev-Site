<template>
    <div class="container">
        <p class="first-p">Vídeos novos toda <span>quinta</span> às <span>20hrs</span></p>
        <img class="img-inscreva" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/subscribe.svg" alt="youtube-inscreva-se">
        <p>www.youtube.com/webdevoficial</p>
    </div>
</template>
<script>
export default {
    name:"Home"
}
</script>
<style>
    .container{
        height: 84vh;
        background-color: #344960;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    
    .img-inscreva {
        margin: 20px 0;
    }
    
    p{
        color: white
    }
    p span{
        font-weight: bold;
    }
</style>