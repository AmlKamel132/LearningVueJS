### Chapter4
#### Indexing, Editing, and Adding Records

------------------------------------------------------------
### 4.1. Creating an index
* in this lesson , we'll add id for each appoinment manually .
* in real projects , we don't make that .
* we define index start with value 0 `aptIndex:0`
* ```Javascript 
      axios.get("./data/appointments.json").then(
      (response) =>
        (this.appointments = response.data.map((item) => {
          item.aptId = this.aptIndex; // add new property called aptindex 
          this.aptIndex++; // increment our index
          return item;
        }))); ```


-----------------------------------------------------------------------------------------
### 4.2. Editing records
* AppoinmentList components edits 
 * we will add new property `contenteditable` to enable modifiy field 
  * `<span contenteditable="contenteditable">{{ item.petName }}</span> ` 
 * Blur events happen when somebody modifies one of these
 * cause of edit method allocate in parent we will emit un event 
 * so , for example it will be `@blur="$emit('edit', item.aptId, 'petName', $event.target.innerHTML)"`
  * item.aptId => id of appoinment that we will edit 
  * petName => the field that will be edited
  * $event.target.innerHTML => new value for field (that we typed ).
* app.vue edits 
  * we will add new method for edit 
     *   ```Javascript
      editItem(id,field,text){
      const aptIndex= _.findIndex(this.appointments,{
         aptId: id
      });
      this.appointments[aptIndex][field] = text;
    }```
  * we depend on lodash method findIndex to get index of appoinment id 
  *  `<appoinment-list :appointments="appointments" @remove="removeItem"  @edit="editItem"/>`


  ---------------------------------------------------------------------------------------------------------
  ### 4.3. Adding records templates
  * in this lesson , we just add AddAppointment component . 
  
  ```Vue 
  <template>
  <div class="col-12">
    <div class="card textcenter mt-3">
      <div
        class="card-header bg-primary text-white"
        @click="hidepanel = !hidepanel"
      >
        <font-awesome-icon icon="plus" class="mr-3" />Add Appointment
      </div>

      <div class="card-body" :class="{ 'd-none': hidepanel }">
        <form id="aptForm">
          <div class="form-group form-row">
            <label class="col-md-2 col-form-label text-md-right" for="petName"
              >Pet Name</label
            >
            <div class="col-md-10">
              <input
                type="text"
                class="form-control"
                name="petName"
                id="petName"
                placeholder="Pet's Name"
              />
            </div>
          </div>

          <div class="form-group form-row">
            <label class="col-md-2 col-form-label text-md-right" for="ownerName"
              >Pet Owner</label
            >
            <div class="col-md-10">
              <input
                type="text"
                class="form-control"
                id="ownerName"
                placeholder="Owner's Name"
              />
            </div>
          </div>

          <div class="form-group form-row">
            <label class="col-md-2 col-form-label text-md-right" for="aptDate"
              >Date</label
            >
            <div class="col-md-4">
              <input type="date" class="form-control" id="aptDate" />
            </div>
            <label class="col-md-2 col-form-label text-md-right" for="aptTime"
              >Time</label
            >
            <div class="col-md-4">
              <input
                type="time"
                class="form-control"
                name="aptTime"
                id="aptTime"
              />
            </div>
          </div>

          <div class="form-group form-row">
            <label class="col-md-2 text-md-right" for="aptNotes"
              >Apt. Notes</label
            >
            <div class="col-md-10">
              <textarea
                class="form-control"
                rows="4"
                cols="50"
                name="aptNotes"
                id="aptNotes"
                placeholder="Appointment Notes"
              ></textarea>
            </div>
          </div>

          <div class="form-group form-row mb-0">
            <div class="offset-md-2 col-md-10">
              <button type="submit" class="btn btn-primary d-block ml-auto">
                Add Appointment
              </button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
export default {
  name: "AddAppointment",
  data() {
    return {
      hidepanel: true,
    };
  },
  components: {
    FontAwesomeIcon,
  },
};
</script>
<style>
.card-header {
  cursor: pointer;
}
</style>```

* then import AddAppointment in app.vue & use it 
  * ` import AddAppointment from "./components/AddAppointment.vue" `
  * add component to components list 
  * using it ` <AddAppointment /> ` 


  ----------------------------------------------------------------------------------------
### 4.4. Managing form data with V-model
* we'll use here v-model  two way binding 
  *   ` v-model="formData.petOwner" `
* at form we'll add  @submit.prevent="requestAdd" 
  * requestAdd => method name
  * .prevent => our modifier  which equal $event.preventDefault()
  * requestAdd function will be untill 
  ```Javascript 
        this.formData = {
        petName: this.formData.petName,
        petOwner: this.formData.petOwner,
        aptDate: this.formData.aptDate + " " + this.formData.aptTime,
        aptNotes: this.formData.aptNotes,
      }; ```

-----------------------------------------------------------------------------------------------------------
### 4.5. Adding records to your data
* ```Javascript requestAdd() {
      this.formData = {
        petName: this.formData.petName,
        petOwner: this.formData.petOwner,
        aptDate: this.formData.aptDate + " " + this.formData.aptTime,
        aptNotes: this.formData.aptNotes,
      };
      console.log(this.formData);

      this.$emit("add",this.formData);
      this.formData = [];
    }```
 * we'll send data as object 
 * cause add in parent component we will emit new event  `this.$emit("add",this.formData);`
 * then we need delete all values of our form => ` this.formData = [] ` 
* at app.vue 
  * we'll add our method 
    * ```Javascript 
      addItem(appoinment){
        appoinment.aptId = this.aptIndex; // modifiy our object .. add id .. in real projects we won't do that 
        this.aptIndex++;
        this.appointments.push(appoinment); // add new object to our appointments list
    } ```
    * `  <AddAppointment  @add="addItem" /> `




    --------------------------------------------------------------------------------------------------------------------------------