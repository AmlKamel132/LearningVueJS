<template>
  <div class="container mt-5">
    <router-view
      :cart="cart"
      :cartQty="cartQty"
      :cartTotal="cartTotal"
      :products="products"
      :sliderStatus="sliderStatus"
      :maximum.sync="maximum"
      @delete="deleteItem"
      @add="addItem"
      @toggle="toggleSliderStatus"
 ></router-view>
 
  </div>
</template>

<script>

export default {
  name: "App",
  data() {
    return {
      products: null,
      maximum: 99,
      sliderStatus: true,
      cart: [],
    };
  },
  mounted: function () {
    fetch("https://hplussport.com/api/products/order/price")
      .then((response) => response.json())
      .then((data) => {
        this.products = data;
      })
      .catch((error) => {
        console.error("Error:", error);
      });
  },
  methods: {
    addItem: function (product) {
      var productIndex;
      var isExisting = this.cart.filter(function (item, index) {
        if (item.product.id == Number(product.id)) {
          productIndex = index;
          return true;
        } else {
          return false;
        }
      });

      if (isExisting.length) {
        this.cart[productIndex].qty++;
      } else {
        this.cart.push({ product: product, qty: 1 });
      }
    },
    deleteItem: function (index) {
      if (this.cart[index].qty > 1) {
        this.cart[index].qty--;
      } else {
        this.cart.splice(index, 1);
      }
    },
    toggleSliderStatus() {
      this.sliderStatus = !this.sliderStatus;
    },
  },
  computed: {
    cartQty: function () {
      let qty = 0;
      for (let index in this.cart) {
        qty = qty + this.cart[index].qty;
      }
      return qty;
    },
    cartTotal: function () {
      let total = 0;
      for (let index in this.cart) {
        total = total + this.cart[index].qty * this.cart[index].product.price;
      }
      return total;
    },
  },
};
</script>
