<template>
  <div>
    {{product.name}}
    <button @click="addToCart(product.id)">add to cart</button>
  </div>
</template>

<script>
export default {
  name: 'Product',
  props: {
    product: Object
  },
  methods: {
    addToCart(productId) {
      this.$emit('add-to-cart', { productId })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
