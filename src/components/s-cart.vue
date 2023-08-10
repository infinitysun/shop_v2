<template>
  <div>
    <h1>Cart</h1>
    <ul class="row">
      <li class="col-12 col-md-6 col-lg-4 mb-3"
        v-for="item in carts"
        :key="item.article"
      >
        <sCartItem :cart="item" />
      </li>
    </ul>
  </div>
</template>

<script>
import sCartItem from '@/components/s-cart-item'

export default {
  name: 's-cart',
  props: {
    carts: {
      type: Array,
      default: () => []
    }
  },
  components: {
    sCartItem
  }
}
</script>

<style scoped>

</style>
