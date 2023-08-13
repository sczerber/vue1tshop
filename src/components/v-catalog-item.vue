<template>
<div class="v-catalog-item">
  <h3>Name: Item1</h3>
  <img src="" alt="image">
  <p>Price: 100$</p>
  <button>Add to cart</button>
</div>
</template>

<script>
export default {
  name: "v-catalog-item",
  props: {}
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
</style>
