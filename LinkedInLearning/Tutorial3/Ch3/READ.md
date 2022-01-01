### Chapter3
#### Props,Methods and Events 

------------------------------------------------------------------
### 3.1. Using props in subcomponents
* here we will new component called AppoinmentList  & dispaly appointments info in it 
 ```Vue
 <template>
  <div>
    <div v-for="(item, index) in appointments" :key="index">
      <h4>{{ item.petName }}</h4>
      <p>{{ item.petOwner }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["appointments"],
};
</script>
``` 
* import AppoinmentList in app.vue and use it 
 ```Vue 
 <template>
  <div id="main-app" class="container">
    <appoinment-list :appointments="appointments" />
  </div>
</template>

<script>
import AppoinmentList from "./components/AppoinmentList.vue";
import axios from "axios";

export default {
  name: "MainApp",
  data() {
    return {
      title: "Appointment List",
      appointments: [],
    };
  },
  components: {
    AppoinmentList,
  },
  mounted() {
    axios
      .get("./data/appointments.json")
      .then((response) => (this.appointments = response.data));
  },
};
</script>
 ``` 


------------------------------------------------------------------------------------------------------------------------------
### 3.2. Adding a Bootstrap template
* in this lesson , we'll update AppoinmentList component to be beautiful (adding classes )
```Vue 
<template>
  <div class="col-12 col-md-10 col-lg-7">
    <div class="list-group list-group-flush">
      <div
        class="list-group-item d-flex align-items-start"
        v-for="(item, index) in appointments"
        :key="index"
      >
        <button class="mr-2 btn btn-sm btn-danger">
          <font-awesome-icon icon="trash" />
        </button>
        <div class="w-100">
          <div class="d-flex justify-content-between">
            <span class="h4 text-primary">{{ item.petName }}</span>
            <span class="float-right">{{ item.aptDate }}</span>
          </div>
          <div class="owner-name">
            <span class="font-weight-bold text-primary mr-1">Owner:</span>
            <span>{{ item.petOwner }}</span>
          </div>
          <div>{{ item.aptNotes }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
export default {
  props: ["appointments"],
  components: {
    FontAwesomeIcon,
  },
};
</script>
 ```

------------------------------------------------------------------------------------------------------------------------------------

### 3.3. Using Moment.js for dates
* if you check date that displayed it'll look like 2017-07-24 08:30
* in this lesson we'll use moment to change date format 
 * updates
   * ` import moment from "moment"; `
   * we'll create method that takes date & format it 
    * ``` formattedDate: function(date) {return moment(new Date(date)).format("MM-DD-YY, h:mm a");} ```
    * you can set format date with any format that you need . now date will look like 07-24-17, 8:30 am when using method
  * `<span class="float-right">{{ formattedDate(item.aptDate) }}</span>` using method


  -------------------------------------------------------------------------------------------------------------------------------

### 3.4. Deleting records
 * in this lesson we will start delete record from appoinments
 * cause delete method we'll allocate in app.vue (parent) . we'll emit un event 
 `<button class="mr-2 btn btn-sm btn-danger" @click="$emit('remove', item)"><font-awesome-icon icon="trash" /></button>`
 * also , in app.vue we'll add our method .. here we will use lodash 
  * import it `import _ from 'lodash'`;
  * define our method `removeItem(appoinment){this.appointments = _.without(this.appointments,appoinment);}`
   * notes : it's not required to use lodash to remove items , in previos tutorial we didn't use it .
 * final => `<appoinment-list :appointments="appointments" @remove="removeItem" />`
 * if you want to learn more about  [lodash] => (https://lodash.com/)


 ---------------------------------------------------------------------------------------------------------------------------




