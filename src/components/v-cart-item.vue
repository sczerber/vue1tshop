<template>
<div class="v-cart-item">
  <img
      :src="require('../assets/images/' + cart_item_data.image)"
      alt="image"
      class="item-image"
  />
  <div>
    {{cart_item_data.name}}
  </div>
  <div>
    {{cart_item_data.price}}$
  </div>
  <div>
    {{cart_item_data.category}}
  </div>
  <button @click="deleteFromCart">Delete</button>
</div>
</template>

<script>
export default {
  name: "v-cart-item",
  props: {
    cart_item_data:{
      type: Object,
      default(){
        return {};
      }
    }
  },
  methods: {
    deleteFromCart() {
      this.$emit('deleteFromCart');
    }
  }
}
</script>

<style scoped>
.v-cart-item {
  background: lightblue;
  display: flex;
}
</style>
