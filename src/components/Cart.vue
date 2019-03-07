<template>
  <div>
    <div v-for="(product, key) in list" :key="key">
      <CartItem v-if="product" :product="product" :id="key" @remove-from-cart="removeFromCart"/>
    </div>
  </div>
</template>

<script>
import CartItem from './CartItem'
export default {
  name: 'Cart',
  props: {
    list: Array
  },
  components: {
    CartItem  
  },
  methods: {
    removeFromCart({ id }) {
      let cart = this.list.slice(0)
      cart.splice(id, 1)
      this.$emit('cart-update', { cart })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
