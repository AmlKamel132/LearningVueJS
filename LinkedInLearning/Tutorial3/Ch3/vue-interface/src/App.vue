<template>
  <div id="main-app" class="container">
    <div class="row justify-content-center">
     <appoinment-list :appointments="appointments" @remove="removeItem" />
    </div>
  </div>
</template>

<script>
import AppoinmentList from "./components/AppoinmentList.vue";
import axios from "axios";
import _ from 'lodash'

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
  methods:{
    removeItem(appoinment){
      this.appointments = _.without(this.appointments,appoinment);
    }

  }
};
</script>
