<template>
<div class="v-main-wrapper">
    <router-view></router-view>


</div>
</template>

<script>
import {mapGetters} from 'vuex'

export default {
  name: "v-main-wrapper",
  props: {},
  data() {
    return {
      title: "Main wrapper component"
    }
  },
  computed: {
    ...mapGetters(['CART']),
  }
}
</script>

<style scoped>
  .v-main-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px 0;
  }
</style>
