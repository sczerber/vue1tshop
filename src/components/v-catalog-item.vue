<template>
<div class="v-catalog-item">
  <h3>Name: {{product_data.name}}</h3>
  <img :src="require('../assets/images/' + product_data.image)" alt="image" class="item-image">
  <p class="v-catalog-item__price">Price: {{product_data.price}}$</p>
  <button @click="addToCart">Add to cart</button>
</div>
</template>

<script>
export default {
  name: "v-catalog-item",
  props: {
    product_data: {
      type: Object,
      default() {
        return {};
      }
    }
  },
  methods: {
    addToCart(){
      this.$emit('addToCart', this.product_data)
    }
  }
}
</script>

<style scoped>
  .v-catalog-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
    border-radius: 4px;
    box-shadow: 0px 0px 7px 0px #000000;
  }
  .v-catalog-item img {
    max-width: 100%;
  }
  .v-catalog-item__price {
    margin-top: auto;
    padding-top: 10px;
  }
  h3 {
    font-size: 16px;
  }
</style>
