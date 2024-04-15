<script>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
import AppContent from './components/AppContent.vue';
import axios from 'axios';
import { store } from './store.js'

  export default {
    components: {
      AppHeader,
      AppFooter,
      AppContent,

    },
    methods: {
      fetchProducts(){
        axios.get('http://localhost:3000/products').then((res) => {
          store.products = res.data
        })
      }
    },
    created(){
      this.fetchProducts()
    }
  }
</script>

<template>
<AppHeader/>
<AppContent/>
<AppFooter/>

</template>

<style lang="scss">
@use './style/general.scss'
</style>
