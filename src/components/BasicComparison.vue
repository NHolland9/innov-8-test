<template>
  <section class="basic-comparison">

    <div>
      <h3>Grip</h3>
      <div class="basic-comparison__item-wrapper">
        <p class="basic-comparison__item-title">snow & ice</p>
        <div class="basic-comparison__stat-wrapper">
          <div class="basic-comparison__stat">
            <div v-for="index in pick1.grip[0].snowIce" :key="`${index}-pick1-snowIce`" class="basic-comparison__stat-number"></div>
          </div>
          <div class="basic-comparison__stat">
            <div v-for="index in pick2.grip[0].snowIce" :key="`${index}-pick2-snowIce`" class="basic-comparison__stat-number"></div>
          </div>
        </div>
      </div>
      
      <div class="basic-comparison__item-wrapper">
        <p class="basic-comparison__item-title">soft & muddy</p>
        <div class="basic-comparison__stat-wrapper">
          <div class="basic-comparison__stat">
            <div v-for="index in pick1.grip[0].softMuddy" :key="`${index}-pick1-softMuddy`" class="basic-comparison__stat-number"></div>
          </div>
          <div class="basic-comparison__stat">
            <div v-for="index in pick2.grip[0].softMuddy" :key="`${index}-pick2-softMuddy`" class="basic-comparison__stat-number"></div>
          </div>
        </div>
      </div>
      
      <div class="basic-comparison__item-wrapper">
        <p class="basic-comparison__item-title">hard & rocky</p>
        <div class="basic-comparison__stat-wrapper">
          <div class="basic-comparison__stat">
            <div v-for="index in pick1.grip[0].hardRocky" :key="`${index}-pick1-hardRocky`" class="basic-comparison__stat-number"></div>
          </div>
          <div class="basic-comparison__stat">
            <div v-for="index in pick2.grip[0].hardRocky" :key="`${index}-pick2-hardRocky`" class="basic-comparison__stat-number"></div>
          </div>
        </div>
      </div>
      
      <div class="basic-comparison__item-wrapper">
        <p class="basic-comparison__item-title">paths & trails</p>
        <div class="basic-comparison__stat-wrapper">
          <div class="basic-comparison__stat">
            <div v-for="index in pick1.grip[0].pathsTrails" :key="`${index}-pick1-pathsTrails`" class="basic-comparison__stat-number"></div>
          </div>
          <div class="basic-comparison__stat">
            <div v-for="index in pick2.grip[0].pathsTrails" :key="`${index}-pick2-pathsTrails`" class="basic-comparison__stat-number"></div>
          </div>
        </div>
      </div>
      
      <div class="basic-comparison__item-wrapper">
        <p class="basic-comparison__item-title">road</p>
        <div class="basic-comparison__stat-wrapper">
          <div class="basic-comparison__stat">
            <div v-for="index in pick1.grip[0].road" :key="`${index}-pick1-road`" class="basic-comparison__stat-number"></div>
          </div>
          <div class="basic-comparison__stat">
            <div v-for="index in pick2.grip[0].road" :key="`${index}-pick2-road`" class="basic-comparison__stat-number"></div>
          </div>
        </div>
      </div>
    </div>

  </section>
</template>

<script>
export default {
  name: 'BasicComparison',

  props: {
    pick1: {
      type: Object,
    },
    pick2: {
      type: Object,
    }
  },

  data() {
    return {
      // pick1: productData
    }
  }
}
</script>

<style lang="scss" scoped>

  .basic-comparison {

    &__item-wrapper {
      margin-bottom: 12px;
    }

    &__item-title {
      padding-bottom: 4px;
      font-size: 0.8em;
      font-weight: bold;
      text-transform: uppercase;
    }

    &__stat-wrapper {
      display: flex;
      justify-content: center;
      height: 8px
    }

    &__stat {
      width: 50%;
      margin: 0 2px;
      display: flex;

      &:first-child {
        justify-content: flex-end;

        .basic-comparison__stat-number {
          background-color: #0f0;
        }
      }
    }

    &__stat-number {
      height: 100%;
      width: 20px;
      background-color: red;
      margin: 0 4px;
    }
  }

</style>