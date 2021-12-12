### Chapter 1
### Vue.js Overview
------------------------------------------------------------------------------------------------------------------------------

## 1.1 Basic Installation

* as we did in tutorial 1 we will use cdn but here we will use v2 not v3 -- we use developement version cause it  with full warnings and debug mode -- 

---------------------------------------------------------------------------------------------------------------------------
## 1.2 Reactive data

*  the features that make VueJS super special. 
*  the code you write in VueJS is reactive, which means that once you create a reference to some data, that reference is actually connected to the data, and reacts to change this.
* if we were working with HTML, I would have to target an element in the DOM, and do something like get element by ID, and then do something like modify the inner HTML or the inner text, but with something like VueJS whenever you modify the data, it takes care of updating the layout and the design of the page for you, and that's one of the reasons why it's so powerful.

-----------------------------------------------------------------------------------------------------------------------------------
 ### 1.3 Binding data to attributes

 * like we did in tutorial1 we bind attribute using v-bind:attribute or :attribute example :src="" 

 ----------------------------------------------------------------------------------------------------------------------------------

 ### 1.4 Looping through data

 * Vue Provide Directive to loop through array v-for 

 -----------------------------------------------------------------------------------------------------------------------------------
 ### 1.5 Conditional data

 * here we just use v-if to check our condition 

 -----------------------------------------------------------------------------------------------------------------------------------

 ### 1.6 Handing user input
 * in our example we'll use v-model instead of :value , as we mentioned in tutorial1 v-model two way binding but, :value one way binding


 ------------------------------------------------------------------------------------------------------------------------------------
 
  ### 1.7 Lifecycle hooks
  ### Notes : (From Documentation )

 * All lifecycle hooks automatically have their this context bound to the instance, so that you can access data, computed properties, and methods. This means you should not use an arrow function to define a lifecycle method (e.g. created: () => this.fetchTodos()). The reason is arrow functions bind the parent context, so this will not be the component instance as you expect and this.fetchTodos will be undefined. (check lesson7_hooks.html file )

* in lesson7 we will use only mounted hook 

* also , we'll use Fetch API, just because it's easiest ( Notes : Fetch not work in some version of Internet Explorer).

---------------------------------------------------------------------------------------------------------------------------------

### 1.8 Events & Methods 
 * Here we define our first addToCart it just push product in cart array 


 ------------------------------------------------------------------------------------------------------------------------------------

### Chapter1 End 
* this tutorial depend on you've knoweldge about vuejs .. so ,we go faster than tutorial 1 .. most of lessons i jsut mentioned what we'll use without go deeply .. cause we did that in tutorial1

* maybe alot of things is repeated , and you know about it .. but if you check lesson8 you will find that we built simple real shopping cart (it's not complete untill now , but it's easy to buil it by easy steps ).




-------------------------------------------------------------------------------------------------------------------------------







