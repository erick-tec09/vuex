<template>
  
 <Header/>
 <Herodetalls/>



 <Footer/>

</template>

<script>
// @ is an alias to /src

import Header from '@/components/Header.vue'
import Herodetalls from '@/components/Herodetalls.vue'

import Footer from '@/components/Footer.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Herodetalls,
 
    Footer
  },
  data() {
      return {
            id: this.$route.params.id
      }
  },

  
}
</script>
