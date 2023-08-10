<template>
  <ul class="row">
    <li
      v-for="product in products"
      :key="product.name"
      class="col-12 col-md-6 col-lg-4 mb-3"
    >
      <sCatalogItem
        :title="product.name"
        :description="product.about"
        :image="`img/${product.image}`"
        :price="product.price"
        :article="product.article"
        @emitAddToCart="addToCart(product)"
      />
    </li>
  </ul>
</template>

<script>
import sCatalogItem from '@/components/s-catalog-item'

export default {
  name: 's-catalog',
  components: {
    sCatalogItem
  },
  data () {
    return {

    }
  },
  computed: {
    products () {
      return this.$store.state.products
    }
  },
  methods: {
    addToCart (val) {
      this.$store.commit('SET_CART', val)
    }
  },
  created () {
    this.$store.dispatch('GET_PRODUCTS')
  }
}
</script>

<style scoped>

</style>
