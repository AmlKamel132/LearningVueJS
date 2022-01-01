### Chapter2
#### Working with modules and data 

------------------------------------------------------
### 2.1. Cleaning up and loading a module
* we'll import bootstrap in main.js 
  * ` import "bootstrap"; `
  * ` import "bootstrap/dist/css/bootstrap.css"; ` 
* also , clean up app.vue 
 ``` JavaScript 
 <template>
  <div id="main-app" class="container">
    <h4>{{title}}</h4>
  </div>
</template>
<script>
export default {
  name: "MainApp",
  data() {
    return {
      title: "Appointment List"
    };
  }
};
</script>
```
 
 ---------------------------------------------------------------------------------------------------------------
### 2.2. Importing Font Awesome icons
* we'll update main.js & import icons that we'll need in our project 
``` import {library} from "@fortawesome/fontawesome-svg-core"; ```
``` import {faPlus, faMinus, faTrash, faCheck} from "@fortawesome/free-solid-svg-icons"; ```
``` library.add(faPlus, faMinus, faTrash, faCheck); ```
* we'll update app.vue to use plus-icon 
 * import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
 * add FontAwesomeIcon to components ` components: {FontAwesomeIcon}`
 * using it ``` <font-awesome-icon icon="plus" /> ``` (notes => here we use kabab case instead of camel case of component name )
```JavaScript 
<template>
  <div id="main-app" class="container">
    <h4>{{ title }}</h4>
    <font-awesome-icon icon="plus" class="mr-2" />Add Appointment
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

export default {
  name: "MainApp",
  data() {
    return {
      title: "Appointment List",
    };
  },
  components: {
    FontAwesomeIcon,
  },
};
</script>
``` 

-------------------------------------------------------------------------------------------------------------------------------------
### 2.3. Looping through data with directives
* we used v-for many times to loop through array . and we will use it here .

```javascript
<template>
  <div id="main-app" class="container">
    <h4>{{ title }}</h4>
    <font-awesome-icon icon="plus" class="mr-2" />Add Appointment
    <div v-for="(item,index) in appointments" :key="index">
      <h4>{{item.petName}}</h4>
      <p>{{item.petOwner}}</p>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

export default {
  name: "MainApp",
  data() {
    return {
      title: "Appointment List",
      appointments: [
        
          {
            petName: "Spot",
            petOwner: "Constance Smith",
            aptDate: "2017-07-24 08:30",
            aptNotes: "This German Shepherd is having some back pain",
          },
          {
            petName: "Goldie",
            petOwner: "Barot Bellingham",
            aptDate: "2017-07-22 15:50",
            aptNotes: "This Goldfish has some weird spots in the belly",
          },
          {
            petName: "Mitten",
            petOwner: "Hillary Goldwyn",
            aptDate: "2017-07-21 9:15",
            aptNotes: "Cat has excessive hairballs",
          },
          {
            petName: "Buffy",
            petOwner: "Hassum Harrod",
            aptDate: "2017-07-20 15:30",
            aptNotes:
              "This Chihuahua has not eaten for three days and is lethargic",
          },
        ],
      
    };
  },
  components: {
    FontAwesomeIcon,
  },
};
</script>
```


------------------------------------------------------------------------------------------------------------------------------------
### 2.4. Using Axios to import data
* in tutorial2 we used fetch . here we'll use axios .
* updates 
 * we will create folder with name (data) in public folder
 * adding new file called appointments.json 
 * moving appointments from app.vue to appointments.json 
 * import axios to use it ` import axios from "axios"; `
 * using axios to fetch data 
  ``` mounted() {
    axios
      .get("./data/appointments.json")
      .then((response) => (this.appointments = response.data));
  } ``` 



  -------------------------------------------------------------------------------------------------------------------------------
  