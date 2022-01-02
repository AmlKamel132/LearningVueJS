<template>
  <div id="main-app" class="container">
    <div class="row justify-content-center">
      <AddAppointment  @add="addItem" />
      <appoinment-list :appointments="appointments" @remove="removeItem"  @edit="editItem"/>
    </div>
  </div>
</template>

<script>
import AppoinmentList from "./components/AppoinmentList.vue";
import AddAppointment from "./components/AddAppointment.vue"
import axios from "axios";
import _ from "lodash";

export default {
  name: "MainApp",
  data() {
    return {
      title: "Appointment List",
      appointments: [],
      aptIndex: 0,
    };
  },
  components: {
    AppoinmentList,
    AddAppointment
  },
  mounted() {
    axios.get("./data/appointments.json").then(
      (response) =>
        (this.appointments = response.data.map((item) => {
          item.aptId = this.aptIndex;
          this.aptIndex++;
          return item;
        })));
  },
  methods: {
    removeItem(appoinment) {
      this.appointments = _.without(this.appointments, appoinment);
    },
    editItem(id,field,text){
      const aptIndex = _.findIndex(this.appointments,{
         aptId: id
      });

     this.appointments[aptIndex][field] = text;

    },
    addItem(appoinment){
        appoinment.aptId = this.aptIndex;
        this.aptIndex++;
        this.appointments.push(appoinment);
    }
  },
};
</script>
