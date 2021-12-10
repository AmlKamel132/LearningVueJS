### Tutorial 1 (This Tutorial With Name Learning Vue Js By Michael Sullivan) (VueJS 3)

---------------------------------------------------------------------------------
#### 1.1 How To Add Vue In Your Application 
if u go to vue documentation you can find more than way to add it , but we will use cdn now .

----------------------------------------------------------------------------------

### 1.2 Render Dynmaic Data To Our DOM 
* the way we did here using {{  }} double curly braces to display our data .
* you can do alot of things depend on value example  (Check render_data File , Not Rleated With Tutorial  )

------------------------------------------------------------------------------------------------------------

### 1.3  Binding to inner text and HTML
* v-html we use it to bind html 
* v-text we use it to bind inner text 

--------------------------------------------------------------------------------------------------------------
### 1.4 Binding property 
* v-bind:property == :property , example :href="{{url}}" 
* but case we use :value it bind data from vue to dom which means 
any change in dom will not bind to vue (One Way Bind ), So 
we will use v-model="{{inputVal}}" (Two Way Binding) 
check File (Lesson4)
      
----------------------------------------------------------------------------------------------------------------

### 1.5 Handling Event 
* v-on:event == @event , example @click="DoSomeThing"

----------------------------------------------------------------------------------------------------------------

### Ch2
####  Form Control Binding 
### 2.1 
* Just Example For Two Way Binding using it with input & textarea  


----------------------------------------------------------------------------------------------------------
### 2.2 How To Use CheckBox
* in lesson7.html file you'll find more than case for checkbox 
  * Check Only One CheckBox 
  * How To Check Only One Check Box With customiz value 
  * Check More Than One

----------------------------------------------------------------------------------------------------------

### 2.3 How To Use Radio & Select 
* here we added select & radio buttons to treat with them
* also , in this lesson we learnt how to install VueJs DevTools
  * chroome extension link  https://chrome.google.com/webstore/detail/vuejs-devtools/ljjemllljcmogpfapbkkighbhhppjdbg 
  * add it then if you want pin it 
  * also , go to setting for this extension (Manage Extension ) and Enable Allow access to file URLs
  * Restart Your Browser .
  * if You file after that .. in console you'll find tab with name Vue (You'll Find Root if you click on it , Data Will Appear  (You can Track any change also , you can change any data property ))



----------------------------------------------------------------------------------------------------------------

### 2.4 Modifiers 
 * Modifiers are special postfixes denoted by a dot, which indicate that a directive should be bound in some special way.
   * In Our Example We Use v-model.trim="deckName" , if you type space at the end or at the end of this input & checked value off
     deckName it'll Appear without any space cause of trim that we used 
   * Also , We Use  v-model.number="categoryId" , if you choose any one it will be number .
    Before using number modifiers if you track categoryId value you'll notice that it's string 
  *  on:submit.prevent="Submit" Here We use .prevent modifiers to call event.preventDefault() on the triggered event
  * There's alot of modifiers we just use 3 of it untill now

---------------------------------------------------------------------------------------------------------------------------------


### 2.5 Computed Property
 * MayBe It look like methods but there's difference in performance cause of computed property cached ,
   You'll Find difference in lesson10 file 
 * lesson10 file Not Releated With Tutorial 


 ------------------------------------------------------------------------------------------------------------------------------ 

### 3
### 3.1 Conditional Rendering 
* Here we will use condition to render specific data  v-if ,  also there's Example in lesson11 


--------------------------------------------------------------------------------------------------------------------------------

### 3.2 v-show 
* also, we can use it to display or hide depend on specific data .
* But , v-show it just toggle element's display .. v-if not toggle display it destroy and re-construct 
* lesson12 .. open console if change value of flipped to show what will happen 

--------------------------------------------------------------------------------------------------------------------------------
### 3.3 v-for 
* we use it to render data  (lesson13_tutorial tutorial example)
* lesson13 you can find more than Example 

--------------------------------------------------------------------------------------------------------------------------------
### 3.4 Binding Style Attribute 
*(lesson14_tutorial) we bind style using :style=""

--------------------------------------------------------------------------------------------------------------------------------
### 3.5 Binding Class 
* lesson15_tutorial .. we  can bind style using :class="" 

----------------------------------------------------------------------------------------------------------------------------

### 4 Using Vue Component 
### 4.1 
* lesson16 .. we'll learn how to use components & register it .. simple example 


-----------------------------------------------------------------------------------------------------------------------------
### 4.2 Using component props 
* lesson17 .. cause of child components can't use/access parent's data directly we will use props 

-----------------------------------------------------------------------------------------------------------------------------


