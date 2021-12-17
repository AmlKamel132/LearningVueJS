### Chapter3
### Managening Css Styles
#### Returnning Back To shopping cart 

### 3.1 Binding Classes With Objects Aand Arrays
 * in first lesson we just return back to our shopping cart example 
 * here we use v-bind:class to bind class , v-bind:style to bind style 

 ----------------------------------------------------------------------------------------------------------------
### 3.2 Expressions And Computed Classes 
* we still continue in binding classes .. here we will depend on computed to bind class 

------------------------------------------------------------------------------------------------------------------
### 3.3 Toggling Computed Classes
* we just add new button to toggle sliderStatus 

------------------------------------------------------------------------------------------------------------------
### 3.4 Creating Transitions And Animations
 * Vue.js gives you a great way of animating objects and it's called transitions. (https://vuejs.org/v2/guide/transitions.html)
 * here we will animate the appearance and disappearance of this element that we created a toggler . 
 * first we will use  transition tag ..  also we should add css style to make animation work 

 ----------------------------------------------------------------------------------------------------------
 
 ### 3.5 Using Aan Animation Framework 
 * Another way to create animations for your projects is to use a prebuilt library.
 * we will use one called animate.css https://animate.style/
 * we'll still using transition tag .. but here won't need to css style cause we use library 
   we just tell them what should do/happen wehen enter active class or leave depend on what we want 
   * Ex 
       * enter-active-class="animated fadeInDown"
       * leave-active-class="animated slideOutRight"
    
------------------------------------------------------------------------------------------------------------------------------
 
 ### 3.6 Working With Transition Groups
  *  In order to animate list of items , we're going to need to use a variation of the transitions called transition group. 
  * here we will use transition group tag for our item products 
  * Every Time we use v-for it recommanded to add key attribute => :key for each element -- unique identifier --  like having id in each element .
  * vue js documnentation about key 
   * key attribute is primarily used as a hint for Vue's virtual DOM algorithm to identify VNodes when diffing the new list of nodes against the old list. Without keys, Vue uses an algorithm that minimizes element movement and tries to patch/reuse elements of the same type in-place as much as possible. With keys, it will reorder elements based on the order change of keys, and elements with keys that are no longer present will always be removed/destroyed.


   ----------------------------------------------------------------------------------------------------------------------------------
### 3.7 Managing Styles With Javascript
 *  Transitions and transition groups also create different events that we can track and modify what's happening with our application and our animations. 
 * events look like classes that we used   
    * in our example we used  beforeEnter , enter & leave .. every one of them will execute method that we defined in our methods  
    * what's interesting about these events is that they can receive the individual element as it is being created.


----------------------------------------------------------------------------------------------------------------------------------

### Chapter3 End 
  





      