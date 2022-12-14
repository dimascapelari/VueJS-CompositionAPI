<template>
  <div>Produto</div>
</template>

<script>
import CalculateDiscountMixin from "./CalculateDiscountMixin.vue";

export default {
  mixins: [CalculateDiscountMixin],

  created() {
    this.calculateDiscount();
  },
};
</script>

<style></style>
