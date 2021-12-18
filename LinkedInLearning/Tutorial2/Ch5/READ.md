### Chapter 5
### Component Based Vue 
#### we'll start to create reusable components

-----------------------------------------------------------------------------------------
### 5.1 Creating reusable components
* here we will start to add new component & used it , like we did in tutorial 1
 * price component .. all data in this component are static untill 

-------------------------------------------------------------------------------------------

### 5.2 Using props
* cause of components can't access value of another components directly , we will pass prop 
* Ex:                       
     *  ` <price :value="item.price"  :prefix="'&euro;'" :precision="2" :conversion=".87"></price> `
     * in our component we will define ` props:['value','prefix','precicion','conversion'] `


-----------------------------------------------------------------------------------------------
### 5.3 Prop Options
 * instead of define props as array .. you can define it as object ..  
 * Ex:  ` props: {
                value: Number,
                prefix: {
                    type: String, 
                    default: '$'
                },
                precision: {
                    type: Number, //precision type
                    default: 2 //default value case not passed 
                },
                conversion: {
                    type: Number,
                    default: 1
                }
            } `

------------------------------------------------------------------------------------------------------------

### 5.4  Building complex components
 * we 'll build another component for our product-list 
  * `   <product-list :products="products" :maximum="maximum"></product-list> `
  *  ```javascript 
           Vue.component('product-list', {
            props: ['products', 'maximum'],
            template: `<transition-group name="fade" @beforeEnter="beforeEnter" @enter="enter" @leave="leave">
            <div class="row d-none mb-3 align-items-center" v-for="(item,index) in products" :key="'item'+item.id"
                :data-index="index">
                <div class="row" v-if="item.price<=Number(maximum)">
                    <div class="col-1 m-auto">
                        <button class="btn btn-info" v-on:click="addItem(item)">+</button>
                    </div>

                    <div class="col-4">
                        <img class="img-fluid d-block" :src="item.image" :alt="item.name" />
                    </div>
                    <div class="col">
                        <h3 class="text-info">{{ item.name }}</h3>
                        <p class="mb-0">{{ item.description }}</p>
                        <div class="h5 float-right">
                            <price :value="Number(item.price)" :precision="2"></price>
                        </div>
                    </div>
                </div>
            </div>
          </transition-group>`,
            methods: {
                beforeEnter: function (el) {
                    el.className = "d-none";
                },
                enter: function (el) {
                    var delay = el.dataset.index * 100;
                    setTimeout(function () {
                        el.className = "row d-flex mb-3 align-items-center animated fadeInRight";
                    }, delay);
                },
                leave: function (el) {
                    var delay = el.dataset.index * 100;
                    setTimeout(function () {
                        el.className = "row d-flex mb-3 align-items-center animated fadeOutRight";
                    }, delay);
                }
            }
        }); ```
-----------------------------------------------------------------------------------------------
### 5.5 Emitting events from within components
 * now , if u try to add item to cart will not work .. cause components can't make event click directly to another component 
 * we'll emit an event as we did in tutorial 1
   * old    ` <button class="btn btn-info" @click="addItem(item)">+</button> `
   * Now  ` <button class="btn btn-info" @click="$emit('add',item)">+</button> `
   * also `<product-list :products="products" :maximum="maximum" @add="addItem"></product-list>` -- add the name of event that emitted  , addItem method that will be called when event emitted



   -------------------------------------------------------------------------------------------------------------------------------
   ### Chapter 5 End ...
   ##### we finsih & from Chapter 6 we will using vue cli 


   
