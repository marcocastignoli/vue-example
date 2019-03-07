<template>
  <div>
    {{product.name}}
    <button @click="removeFromCart(id)">remove from cart</button>
  </div>
</template>

<script>
export default {
  name: 'CartItem',
  props: {
    product: Object,
    id: Number
  },
  methods: {
    removeFromCart(id) {
      this.$emit('remove-from-cart', { id })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
