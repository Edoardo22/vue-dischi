<template>
  <div id="app">
    <MainSite></MainSite>
  </div>
</template>

<script>
import MainSite from './components/MainSite.vue'
import 'bootstrap/dist/css/bootstrap.min.css';

export default {
  name: 'App',
  components: {
    MainSite,
  }
}
</script>

<style lang="scss">
#app {}
</style>
