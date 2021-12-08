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
* v-on:event == @event , example @clikc="DoSomeThing"

--------------------------------------------------------------------------------------------------------------------
 



