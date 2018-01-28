<template>
  <div id="britecoreApp">
    <bc-navbar></bc-navbar>
    <bc-header :message="header"></bc-header>
    <router-view/>
  </div>
</template>

<script>
import Navbar from './components/Navbar'
import Header from './components/Header'

export default {
  name: 'App',
  data () {
    return {
      header: 'Commercial Property - Add Field'
    }
  },
  components: {
    'bc-navbar': Navbar,
    'bc-header': Header
  }
}
</script>
<style lang="scss">
@import './assets/scss/base';
</style>
