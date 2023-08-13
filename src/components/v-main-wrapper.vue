<template>
<div class="v-main-wrapper">
  <p>{{title}}</p>
  <v-catalog/>
  <v-cart/>
</div>
</template>

<script>
import vCatalog from './v-catalog'
import vCart from './v-cart'

export default {
  name: "v-main-wrapper",
  components: {vCatalog, vCart},
  props: {},
  data() {
    return {
      title: "Main wrapper component"
    }
  }
}
</script>

<style scoped>
  .v-main-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
