<template>
  <div class="wrapper">
    <div class="products">
      <div class="product" v-for="item in products" :key="item.id">
        <div class="info">
          <h1>{{ item.name }}</h1>
          <p>{{ item.country }}</p>
        </div>
        <div class="image">
          <img :src="'/images/products/' + item.image" />
        </div>
        <div class="price">
          <!-- <h2>{{ item }} x {{ item.price }}</h2> -->
          <button @click="RemoveFromCart(item)" class="auto">Remove</button>
          <!-- <button v-show="item != 1" @click="RemoveOne(item)" class="auto">
            Remove One
          </button> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CartList",
  props: {
    products: Array,
  },
  methods: {
    RemoveFromCart(item) {
      this.$root.$data.cart = this.$root.$data.cart.filter(
        (object) => item != object
      );
    },
    // RemoveOne(item) {
    //   let dummy = "";
    //   item -= 1;
    //   this.$root.$data.cart.push(dummy);
    //   this.$root.$data.cart.pop();
    // },
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #f2921d;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
}

.info h2 {
  font-size: 14px;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

.price {
  display: flex;
}

button {
  height: 50px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>