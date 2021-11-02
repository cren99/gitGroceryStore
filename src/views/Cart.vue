<template>
  <div>
    <h1>Added To Cart:</h1>
    <CartList :products="cart" />

    <!-- <h2>Hello its me</h2> -->
  </div>
</template>

<script>
import CartList from "../components/CartList.vue";
export default {
  name: "Browse",
  components: {
    CartList,
  },
  computed: {
    cart() {
      return this.$root.$data.cart;
    },
  },
};
</script>