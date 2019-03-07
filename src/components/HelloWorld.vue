<template>
  <div class="hello">
    <Cart :list="cart" @cart-update="updateCart"/>
    <div v-for="product in products" :key="product.id">
      <Product :product="product" @add-to-cart="buy"/>
    </div>
  </div>
</template>

<script>
import Product from './Product'
import Cart from './Cart'

export default {
  name: 'Inventory',
  methods: {
    buy({ productId }) {
      this.cart.push(this.products.find(p => p.id === productId))
    },
    updateCart({ cart }) {
      this.cart = cart.slice(0)
    }
  },
  data: function() {
    return {
      asd: 'ciao',
      products: [
        { id: 1, name: 'Pizza' },
        { id: 2, name: 'Kebab' },
        { id: 3, name: 'Wurstel' },
      ],
      cart: []
    }
  },
  components: {
    Product,
    Cart
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
