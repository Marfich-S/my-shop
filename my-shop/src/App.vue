<template>
  <div id = "app">
    <router-view />
    <FooterComponent />
  </div>  
</template>

<script>
import FooterComponent from './components/FooterComponent.vue';


export default {
  name: 'App',
  components: {
    FooterComponent,
  }
}
</script>

