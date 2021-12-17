### Chapter4
### Diggeing Deeper 

### 4.1 Filters 

* Filters that can be used to apply common text formatting.
* Filters are usable in two places: mustache interpolations and v-bind expressions  
  * {{ total | currency }}
  * <p v-bind:price="total | currency"></p>
* what we mentioned here releated with vue js 2 , cause of if you check vuejs 3 , filter are removed & recommanded to use methods or computed property also the way of global filters in vuejs2 different from vuejs3 we 'll use it later 
* cause of current we use vuejs 2 we'll learn how to use it , in our example we create filter called currency which will format total 

-----------------------------------------------------------------------------------------------------------------------------------

### 4.2 Toggling elements with a key
* there's no thing new in vue .. here we just dropdown menu that will display elements that we added in cart 

-----------------------------------------------------------------------------------------------------------------------------------
### 4.3 Categorizing lists 
* in lesson2 .. we displayed our cart .. if you add the same item more than one .. it will appear as new element .
 in real cart that's not happen so , we will make some improvements 
   * adding cart method  => first we check if exist or not .. case exist we will increment item's quantity
   *  display cart items => price will be item's price * item's quantity

-----------------------------------------------------------------------------------------------------------------------------
### 4.4 Adding computed classes
* here we'll adding two computed property one of them to calc cart total & another to calc quantity

-----------------------------------------------------------------------------------------------------------------------------

### 4.5 Deleting items and modifiers
 * delete item from cart .. 
   * case item quantity == 1 we'll remove it from cart 
   * case item quantity > 1 , we'll decrement quantity
 * Notes => you can make delete item delete item from cart whatever quantity (it depend on app scenario) , most websites make decrement differnt from delete ..
 * modifiers : we used more than modifiers in tutorial 1 .. here we will use stop modifiers stop == event.stopPropagation() in js


 -------------------------------------------------------------------------------------------------------------------------------

 ### Chapter4 End 
 

