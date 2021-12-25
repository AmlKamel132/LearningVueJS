<template>
  <nav class="navbar navbar-light fixed-top">
    <div class="navbar-text ml-auto d-flex">
      <button
        class="btn btn-sm btn-outline-success"
        @click="$emit('toggle')"
      >
        <font-awesome-icon icon="dollar-sign"></font-awesome-icon>
      </button>

      <div class="dropdown ml-2" v-if="cart.length > 0">
        <button
          class="btn btn-success btn-sm dropdown-toggle"
          id="cartDropdown"
          data-toggle="dropdown"
          aria-haspopup="true"
          aria-expanded="false"
        >
          <span class="badge badge-pill badge-light">{{ cartQty }}</span>
          <!-- <i class="fas fa-shopping-cart mx-2"></i> -->
          {{ cartTotal }}
        </button>

        <div
          class="dropdown-menu dropdown-menu-right"
          aria-labelledby="cartDropdown"
        >
          <div v-for="(item, index) in cart" :key="index">
            <div class="dropdown-item-text text-nowrap text-right">
              <span
                class="badge badge-pill badge-warning align-text-top mr-1"
                >{{ item.qty }}</span
              >
              {{ item.product.name }}
              <Price :value="Number(item.product.price * item.qty)"> </Price>

              <a
                href="#"
                @click.stop="$emit('delete',index)"
                class="badge badge-danger text-white"
                >-</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import Price from "./Price.vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

export default {
  props: ["cart", "cartQty", "cartTotal"],
  components: {
    FontAwesomeIcon,
    Price,
  },
};
</script>
