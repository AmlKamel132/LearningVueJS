<template>
  <transition
    name="custome"
    enter-active-class="animated fadeInDown"
    leave-active-class="animated slideOutRight"
  >
    <div v-if="sliderStatus">
      <div class="align-items-center" :class="sliderState">
        <label :class="labelArr" for="formMax">max</label>
        <input
          type="text"
          id="formMax"
          class="form-control mx-2 text-center"
          :style="{ width: inputWidth + 'px', 'text-align': 'center' }"
          v-model="maxAmount"
          @change="$emit('update:maximum', maxAmount)"
        />
        <input
          type="range"
          class="custom-range"
          min="0"
          max="200"
          v-model="maxAmount"
          @input="$emit('update:maximum', maxAmount)"
        />
      </div>
    </div>
  </transition>
</template>
<script>
export default {
  props: ["sliderStatus"],
  data() {
    return {
      labelArr: ["font-weight-bold", "mr-2"],
      inputWidth: 60,
      maxAmount: 99,
    };
  },
  computed: {
    sliderState: function () {
      return this.sliderStatus ? "d-flex" : "d-none";
    },
  },
};
</script>