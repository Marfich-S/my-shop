<template>
  <div id = "app">
    <ProductList />
    <ReviewsComponent />
    <FooterComponent />
  </div>  
</template>

<script>
import FooterComponent from './components/FooterComponent.vue';
import ProductList from './components/ProductList.vue';
import ReviewsComponent from './components/ReviewsComponent.vue';

export default {
  name: 'App',
  components: {
    ProductList,
    FooterComponent,
    ReviewsComponent
  }
}
</script>

