<template>
  <div class="card" style="width: 18rem;">
    <img :src="image" class="card-img-top" alt="...">
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">{{ description }}</p>
      <div class="d-flex justify-content-between items-center">
        <p>Price: ${{ price }}</p>
        <button class="btn btn-primary" @click="addToCart">Add cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 's-catalog-item',
  props: {
    title: {
      type: String,
      default: 'defaulte title'
    },
    description: {
      type: String,
      default: 'defaulte description'
    },
    image: {
      type: String,
      default: 'defaulte image'
    },
    price: {
      type: Number,
      default: 0
    },
    article: {
      type: String,
      required: true
    }
  },
  methods: {
    addToCart () {
      this.$emit('emitAddToCart', this.article)
    }
  }
}
</script>

<style scoped>

</style>
