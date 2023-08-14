<template>

  <div class="v-cart">

    <router-link :to="{name: 'catalog'}">
      <button>Back to catalog</button>
    </router-link>

    <p>This is cart!</p>
    <p v-if="!CART.length">Your cart is empty</p>
    <v-cart-item
    v-for="(item, index) in CART"
    :key="item.article"
    :cart_item_data="item"
    @deleteFromCart="deleteFromCart(index)"
    />
  </div>
</template>

<script>
import vCartItem from './v-cart-item'
import {mapActions} from 'vuex'
import {mapGetters} from 'vuex'

export default {
  name: "v-cart",
  components: {
    vCartItem
  },
  props: {
    cart_data:{
      type: Array,
      default() {
        return [];
      }
    }
  },
  computed: {
    ...mapGetters(['CART']),
  },
  methods: {
    ...mapActions(['DELETE_FROM_CART']),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index);
      console.log("deleted" + index);
    },
  }
}
</script>

<style scoped>

</style>
