<template>
  <div>
    <div class="d-flex justify-content-between">
      <h1>My shop</h1>
      <router-link v-if="cartsLen > 0" :to="{ name: 'CartPage'}">Cart: <b>{{ cartsLen }}</b></router-link>
      <div v-else>Cart: <b>0</b></div>
    </div>
    <sCatalog />
  </div>
</template>

<script>
import sCatalog from '@/components/s-catalog'

export default {
  name: 's-main-wraper',
  components: {
    sCatalog
  },
  computed: {
    cartsLen () {
      return this.$store.state.cart.length
    }
  }
}
</script>
