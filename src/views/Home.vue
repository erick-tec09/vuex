<template>
  
 <Header/>
 <Hero/>

 <Card/>

 <Footer/>

</template>

<script>
// @ is an alias to /src

import Header from '@/components/Header.vue'
import Hero from '@/components/Hero.vue'
import Card from '@/components/Card.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Hero,
    Card,
    Footer
  },

  
}
</script>
