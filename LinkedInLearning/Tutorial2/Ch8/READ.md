### Chapter 8
### Using the vue Router 
#### Router introduction 
#### Tutorial 2 End 

-----------------------------------------------------------------------------------------
### 8.1. Reorganizing hierarchy
* in this we will reorganize components , in order to use routing .
* we'll create component called Products & move app.vue template to it 
* after moving and run project . if you try to add item to cart will not work 
  * before update we were $emit event directly to parent which was app.vue 
  * now component for example productlist has product parent but method that we need at app which is parent for product
  * so instead of using `$emit` we'll use `$parent.$emit` => `@click.stop="$parent.$emit('delete',index)" `
  * if methods located at product component we won't change any thing . 


----------------------------------------------------------------------------------------------------------------------

### 8.2. Creating a checkout page
* in this lesson we just cart new component called checkout -- display info in cart -- 
* update app.vue -- import check component -- 
* ```JavaScript 
<template>
  <div class="container mt-5">
    <Checkout
      :cart="cart"
      :cartQty="cartQty"
      :cartTotal="cartTotal"
      @delete="deleteItem"
      @add="addItem"
    ></Checkout>
    <products
      :cart="cart"
      :cartQty="cartQty"
      :cartTotal="cartTotal"
      :products="products"
      :sliderStatus="sliderStatus"
      :maximum.sync="maximum"
      @toggle="toggleSliderStatus"
      @delete="deleteItem"
      @add="addItem"
    ></products>
  </div>
</template>

<script>
import Products from "./components/Products.vue";
import Checkout from "./components/Checkout.vue";
export default {
  name: "App",
  components: {
    Products,
    Checkout,
  },
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
</script>``` 

---------------------------------------------------------------------------------------------------------------
### 8.3. Building your routes
 * in this lesson we will create our routes ..
 * we will made updates in main.js -- i perfer to make separate file for routing -- but i'll follow instructor steps .
   * import vueRouter 
    * `import VueRouter from "vue-router";`
    * using vuerouter ` Vue.use(VueRouter); ` => tell vue we'll use VueRouter
    * define our components 
                     ```javascript 
                       const router = new VueRouter({
                          routes: [
                           {
                              path: "/checkout",
                              component: Checkout
                          },
                          {
                               path: "*", //default .. type any thing 
                               component: Products
                          }
                          ]
                      });
    * here we define our routes path & component ... * means if user type anything that not belongs to any of our routes 
    * last step 
              ``` new Vue({
                 render: (h) => h(App),
                 router
                 }).$mount("#app");  ```

    * in app.vue we will use router-view  =>  the view where the components are rendered. it's look like the main div that contain all the components and it return the component that matches the current route.
    * if we want add link to go to specific route we will used router-link `  <router-link to="/checkout" >Checkout</router-link>`

    --------------------------------------------------------------------------------------------------------------------------------

    ### Chater7 End
    ### Tutorial2 End
    ##### Tutorial2
              * we go step by step -- maybe there's info that we know from tutorial1 -- but we go in real example 
              * when i'm learning , i prefer to do the same as instructor do -- for example i prefer to make routes in separate file . sometimes i learnt new organizing hierarchy .

----------------------------------------------------------------------------------------------------------------------------------
      



 