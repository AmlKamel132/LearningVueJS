   <template>
  <span>
    {{ prefix + Number.parseFloat(value * conversion).toFixed(precision) }}
  </span>
</template>
<script>
export default {
  props: {
    value: Number,
    prefix: {
      type: String, // type of prop
      default: "$", // //default value case not passed
    },
    precision: {
      type: Number,
      default: 2,
    },
    conversion: {
      type: Number,
      default: 1,
    },
  },
};
</script>


   
 