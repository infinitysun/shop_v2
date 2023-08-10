<template>
  <div class="cart">
    <h1><router-link :to="{ name: 'HomePage'}">My shop</router-link></h1>
    <sCart v-if="carts.length > 0" :carts="carts" />
    <div v-else>Cart is empty</div>
  </div>
</template>

<script>
import sCart from '@/components/s-cart'

export default {
  components: {
    sCart
  },
  computed: {
    carts () {
      return this.$store.state.cart
    }
  }
}
</script>
