<script>

import { store } from './data/store';
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
  data(){
    return {
      store,
      message: 'Hello there!'
    }
  }
}
</script>

<template>
  <Header />
  <Main />
  <Footer />
  
</template>

<style lang="scss">
@use './scss/main.scss'

</style>