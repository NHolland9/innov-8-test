<template>
  <p>{{testData}}</p>
</template>

<script>
export default {
  props: {
    productData: {
      // type: Object,
      required: true
    }
  },

  data() {
    return {
      testData: this.productData
    }
  }
}
</script>