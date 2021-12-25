### Chapter 7
### Project with the build tool

--------------------------------------------------

### 7.1. Create components
* we will start to convert our example 
 * in chapter 5 , we had component called price , here we will add new component Price 
* also , we'll update our app.vue 
  * we just import our component price 
  ```JavaScript
   <template>
  <div  class="container mt-5">
     <h1>My Shop</h1>
    <p class="animated fadeInRight">our prods</p>
    <font-awesome-icon icon="shopping-cart"></font-awesome-icon>
    <price value="4.52"></price>
  </div>
</template>
<script>
import {FontAwesomeIcon} from '@fortawesome/vue-fontawesome';
import Price from "./components/Price.vue";
export default {
  name: "App",
  components: {
    FontAwesomeIcon,
    Price
  },
};
</script>
``` 

------------------------------------------------------------------------------------------------------------------------------------

### 7.2 Managing complex component

* here we will work with product component 
 * i go back to chapter and take the same code of product-list , also we need to use Price component so i import it and use in our component
 * we will update also , app.vue 
 ```JavaScript 
<template>
  <div class="container mt-5">
    <h1>My Shop</h1>
    <ProductList :maximum="maximum" :products="products" />
  </div>
</template>

<script>
import ProductList from "./components/ProductList.vue";
export default {
  name: "App",
  components: {
    ProductList,
  },
  data() {
    return {
      products: null,
      maximum: 99,
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
};
</script>
``` 

------------------------------------------------------------------------------------------------------------------------------------
### 7.3. Using the Chrome DevTools
 * in this lesson we will learn how to install chrome dev tools -- i mentioned it at turtorial1 -- 
  * chroome extension link https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg
  * after adding it you can pin it if you wanted -- i prefer to pin it , cause when i go to any website that used vuejs i know from it . it shines with green color
  * then , go to setting for this extension (Manage Extension) and Enable Allow access to file URLs
  * Restart Your Browser . -- sometimes it work directly , sometimes it need to restart -- 
  * if you make inspect  you'll find tab with name Vue (You'll Find Root if you click on it  => then every time you clicke on elemnt you can see data & props & change any value if you want as test  ))


  --------------------------------------------------------------------------------------------------------------------------------
  ### 7.4.  Emitting updates 
   * we will create new component PriceSlider 
   * the new thing is that the emit way `@change="$emit('update:maximum', maxAmount)"`
   * also , in app.vue `  <PriceSlider  :sliderStatus="sliderStatus" :maximum.sync="maximum" /> ` 
    * if we pass maximum as props to PriceSlider -- PriceSlider will not able to change maximum value -- ,
    * so what made here is that we define data property called maxAmount in PriceSlider component
    * every time maxAmount updated we emit/trigger an event 
    * .sync listen to event and update maximum at app.vue

    -------------------------------------------------------------------------------------------------------------------------
    ### 7.5. Adding Navigation
     * add new component navbar component
     * also , we add our methods & computed property from old code (chapter 5)
     * in app.vue we also, import navbar and used it 



     ---------------------------------------------------------------------------------------------------------------------------


     ### chapter7 End
     #### here we learn about separate components . everyone in separate file. 
