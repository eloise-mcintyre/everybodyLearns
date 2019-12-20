<template>
  <div id="app">
    <HeaderComponent />
    <Welcome />
  </div>
</template>






<script>
import HeaderComponent from './components/HeaderComponent.vue'
import Welcome from './components/Welcome.vue'


export default {
  name: 'app',
  components: {
    HeaderComponent,
    Welcome
  }
}
</script>





<style>
#app {
  font-family: 'Raleway', sans-serif;
}
</style>
