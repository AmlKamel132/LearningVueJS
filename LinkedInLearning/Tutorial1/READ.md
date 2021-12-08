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

