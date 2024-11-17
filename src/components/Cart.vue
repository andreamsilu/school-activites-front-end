<!-- eslint-disable vue/multi-word-component-names -->
<template>
    <div class="container mt-4">
      <h2>Shopping Cart</h2>
      <ul class="list-group">
        <li class="list-group-item" v-for="item in cart" :key="item.id">
          {{ item.subject }} - ${{ item.price }}
          <button class="btn btn-danger btn-sm float-end" @click="removeFromCart(item)">Remove</button>
        </li>
      </ul>
      <button
        class="btn btn-primary mt-3"
        :disabled="cart.length === 0"
        @click="checkout"
      >
        Checkout
      </button>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cart: [],
      };
    },
    methods: {
      removeFromCart(item) {
        const index = this.cart.indexOf(item);
        if (index > -1) this.cart.splice(index, 1);
      },
      checkout() {
        alert("Order submitted!");
      },
    },
  };
  </script>
  