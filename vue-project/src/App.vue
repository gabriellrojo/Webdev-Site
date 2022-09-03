<template> 
  <div>
    <Navbar />
    <RouterView />
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue"
import Footer from "./components/Footer.vue"
import "./styles/styles.css"
export default {
  name: "App",
  components: {
    Navbar,
    Footer
  }
}
</script>


