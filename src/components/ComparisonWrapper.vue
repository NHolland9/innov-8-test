<template>

  <div>
    <form>

      <select v-model="pick1">
        <option value="" disabled selected>Select a comparison</option>

        <template v-for="product in shoeData">
          <option
            :key="product.id"
            :value="product.id"
            v-if="product.id != pick2">
            {{ product.name }}
          </option>
        </template>
      </select>

      <select v-model="pick2">
        <option value="" disabled selected>Select a comparison</option>

        <template v-for="product in shoeData">
          <option
            :key="`${product.id}-2`"
            :value="product.id"
            v-if="product.id != pick1">
            {{ product.name }}
          </option>
        </template>
      </select>

    </form>

    <div class="comparison__image-wrapper">
      <img v-if="pick1" :src="require(`@/assets/${pick1}.jpg`)" />
      <p>VS</p>
      <img v-if="pick2" :src="require(`@/assets/${pick2}.jpg`)" />
    </div>
    <!-- <p>1</p>
    <ProductComparison :productData="shoeData[pick1-1]" />
    <p>2</p>
    <ProductComparison :productData="shoeData[pick2-1]" /> -->
  </div>
  
</template>

<script>
import shoeData from '@/shoeData.json';
// import ProductComparison from '@/components/ProductComparison.vue'

export default {
  name: 'ComparisonWrapper',

  components: {
    // ProductComparison
  },

  data() {
    return {
      shoeData: shoeData.productData,
      pick1: "",
      pick2: ""
    }
  }
  
}
</script>

<style lang="scss" scoped>
  .comparison__image-wrapper {
    display: flex;
  }
</style>