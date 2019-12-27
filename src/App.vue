<template>
  <div id="app">
<!--    <img alt="Vue logo" src="./assets/logo.png">-->
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
      <Index v-bind:products="products" v-on:view-product="viewProduct"/>
  </div>
</template>

<script>
import Index from './components/Index'

export default {
  name: 'app',
  components: {
    Index
  },
    data(){
      return{
          products: [
              {id:1, name: 'Mazda', amount: 150000},
              {id:2, name: 'Toyota', amount: 120000},
              {id:3, name: 'Nissan', amount: 180000},
              {id:4, name: 'Subaru', amount: 220000},
          ],
      }
    },
    methods: {
        viewProduct: function (id) {
            this.products=this.products.filter(product => product.id == id);

        }
    },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
    line-spacing: 1;
}
</style>
