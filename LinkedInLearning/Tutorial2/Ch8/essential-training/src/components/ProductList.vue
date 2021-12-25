<template>
  <transition-group
    name="fade"
    @beforeEnter="beforeEnter"
    @enter="enter"
    @leave="leave"
  >
    <div
      class="row d-flex mb-3 align-items-center"
      v-for="(item, index) in products"
      :key="'item' + item.id"
      :data-index="index"
    >
      <div class="row" v-if="item.price <= Number(maximum)">
        <div class="col-1 m-auto">
          <button class="btn btn-info" @click="$parent.$emit('add', item)">
            +
          </button>
        </div>

        <div class="col-4">
          <img class="img-fluid d-block" :src="item.image" :alt="item.name" />
        </div>
        <div class="col">
          <h3 class="text-info">{{ item.name }}</h3>
          <p class="mb-0">{{ item.description }}</p>
          <div class="h5 float-right">
            <Price :value="Number(item.price)" :precision="2"></Price>
          </div>
        </div>
      </div>
    </div>
  </transition-group>
</template>
<script>
import Price from "./Price.vue";
export default {
  props: ["products", "maximum"],
  methods: {
    beforeEnter: function (el) {
      el.className = "d-none";
    },
    enter: function (el) {
      var delay = el.dataset.index * 100;
      setTimeout(function () {
        el.className =
          "row d-flex mb-3 align-items-center animated fadeInRight";
      }, delay);
    },
    leave: function (el) {
      var delay = el.dataset.index * 100;
      setTimeout(function () {
        el.className =
          "row d-flex mb-3 align-items-center animated fadeOutRight";
      }, delay);
    },
  },
  components: {
    Price,
  },
};
</script>



