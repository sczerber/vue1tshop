<template>
  <router-link :to="{name: 'cart', params:{cart_data: CART}}">
    <div class="v-catalog-cart-icon">
      Your cart items: {{CART.length}}
    </div>
  </router-link>

  <div class="v-catalog">
    <v-catalog-item
        v-for="product in PRODUCTS"
        :key="product.article"
        v-bind:product_data="product"
        @addToCart="addToCart"
    />
  </div>
</template>

<script>
import vCatalogItem from './v-catalog-item'
import {mapActions, mapGetters} from 'vuex'
export default {
  name: "v-catalog",
  components: {vCatalogItem},
  data() {
    return {

    };
  },
  computed: {
    ...mapGetters(['PRODUCTS', 'CART'])
  },
  methods: {
    ...mapActions(['GET_PRODUCTS_FROM_API', 'ADD_TO_CART']),

    addToCart(data) {
      this.ADD_TO_CART(data);
    },
  },
  mounted(){
    this.GET_PRODUCTS_FROM_API()
    .then((response)=>{
      if(response.data){
        console.log("Data accepted")
      }
    })
  }

}
</script>

<style scoped>
.v-catalog {
  display: grid;
  width: 95%;
  max-width: 1040px;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 20px;
}
.v-catalog-cart-icon {
  margin-bottom: 20px;
  position: fixed;
  right: 20px;
  bottom: 20px;
  z-index: 3;
  background: yellow;
  border: black;
  padding: 10px;
}
</style>
