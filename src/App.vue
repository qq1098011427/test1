<template>
  <div id="app">
   
      <v-header></v-header>
      <v-mbx></v-mbx>    
      <v-main></v-main>
      <v-footer></v-footer>
      
  </div>
</template>

<script>
import header from './components/header'
import mbx from './components/mbx'
import footer from './components/footer'
import main from './components/main'
export default {
  name: 'app',
  data() {
    return {}
    },
    components:{
    'v-header':header,
    'v-mbx':mbx,
    'v-footer':footer,
    'v-main':main
  }
}
</script>

<style>

</style>
