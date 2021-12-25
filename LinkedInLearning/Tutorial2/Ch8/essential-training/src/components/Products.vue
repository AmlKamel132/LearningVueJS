<template>
  <div class="container mt-5">
    <h1>My Shop</h1>
    <NavBar :cart="cart" :cartQty="cartQty" :cartTotal="cartTotal" />
    <PriceSlider :sliderStatus="sliderStatus" :maximum.sync="maximum" />
    <ProductList :maximum="maximum" :products="products" />
  </div>
</template>
<script>
import PriceSlider from "./PriceSlider.vue";
import ProductList from "./ProductList.vue";
import NavBar from "./NavBar.vue";

export default {
  props: [
    "products",
    "maximum",
    "cart",
    "cartQty",
    "cartTotal",
    "sliderStatus",
    "sliderState",
  ],
  components: {
    NavBar,
    PriceSlider,
    ProductList,
  },
};
</script>