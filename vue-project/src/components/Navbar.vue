<template>
    <header>
        <nav>
            <RouterLink to="/"><img class="logo" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg" alt="web-dev"></RouterLink>
            <img @click="showMenu" class="menu" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/menu.svg" alt="burguer-menu">
            <ul class="big-screen">
                <li><RouterLink to="/">Home</RouterLink></li>
                <li><RouterLink to="/videos">Vídeos</RouterLink></li>
                <li><RouterLink to="/about">Sobre</RouterLink></li>
                <li><RouterLink to="/contato">Contato</RouterLink></li>
            </ul>
        </nav>
        <div @click="closeMenu" v-show="menuActive" class="container"></div>
        <div @click="closeMenu" v-show="menuActive" class="container-menu">
            <ul>
                <img class="img-logo" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg" alt="w-dev">
                <li><RouterLink to="/">Home</RouterLink></li>
                <li><RouterLink to="/videos">Vídeos</RouterLink></li>
                <li><RouterLink to="/about">Sobre</RouterLink></li>
                <li><RouterLink to="/">Contato</RouterLink></li>
            </ul>       
        </div>
    </header>
</template>

<script>
export default {
    name: "Navbar",
    data(){
        return{
            menuActive: false
        }
    },

    methods: {
        showMenu(){
            this.menuActive = true
        },
        closeMenu(){
            this.menuActive = false
        },
    }
}
</script>

<style scoped>
    header{
        height: 8vh;
        background-color: #2B3D50;
    }
    header nav{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .big-screen{
        display: none
    }
    .logo {
        max-width: 120px;
        margin-top: 5px;
        margin-left: 15px;
    }
    .menu{
        max-width: 40px;
        margin-top: 3px;
        margin-right: 20px
    }
    .container{
        height: 100%;
        width: 40%;
        position: fixed;
        top: 0;
        left: 0;
        background-color: black;
        opacity: 0.8;
    }
    .container-menu{
        position: fixed;
        top: 0;
        right: 0;
        height: 100vh;
        width: 60%;
        background-color: #2B3D50;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .img-logo{
        max-width: 100px;
        margin-top: 20px;
    }
    li{
        text-align: center;
        margin-top: 30px;
    }
    li a{
        color: white;
    }

    .lista-escrita{
        margin-top: 50px;
    }

    @media(min-width: 720px){
        .container,
        .container-menu,
        .menu{
            display: none
        }
        .big-screen{
            display: flex;
        }

        li{
            margin-top: 0;
            margin-right: 30px;
        }
        li:nth-child(4){
            margin-right: 50px;
        }
        .logo{
            margin-left: 30px;
        }

    }

</style>