<template>
  <v-app dark>
    <Toolbar></Toolbar>
    <Kontent />
    <Footer></Footer>
  </v-app>
</template>

<script>
// add side component / audio player if possible
import Toolbar from '../components/Toolbar'
import Footer from '../components/Footer'
import Kontent from '../components/Kontent'
export default {
  components: {
    Toolbar,
    Footer,
    Kontent
  },
  data() {
    return {}
  }
}
</script>
