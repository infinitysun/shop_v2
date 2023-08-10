<template>
  <div>
    <sCatalog />
    <sCart v-if="carts.length > 0" :carts="carts" />
  </div>
</template>

<script>
import sCatalog from '@/components/s-catalog'
import sCart from '@/components/s-cart'

export default {
  name: 's-main-wraper',
  components: {
    sCatalog,
    sCart
  },
  computed: {
    carts () {
      return this.$store.state.cart
    }
  }
}
</script>
