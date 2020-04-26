<template>
  <span class="iCountUp">
    <ICountUp
      :delay="delay"
      :endVal="endVal"
      :options="options"
      @ready="onReady"
    />
  </span>
</template>

<script type="text/babel">
import ICountUp from "vue-countup-v2";
export default {
  name: "demo",
  components: {
    ICountUp
  },
  data() {
    return {
      options: {
        useEasing: true,
        useGrouping: true,
        separator: ",",
        decimal: ".",
        prefix: "",
        suffix: ""
      }
    };
  },
  props: {
    endVal: {
      type: Number,
      default: 30000
    },
    delay: {
      type: Number,
      default: 1000
    }
  },
  methods: {
    onReady: function(instance, CountUp) {
      const that = this;
      instance.update(that.endVal);
    }
  }
};
</script>

<style scoped>
.iCountUp {
  font-size: 80px;
  margin: 0;
  color: #4d63bc;
}
</style>
