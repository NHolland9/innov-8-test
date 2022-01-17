<template>
  <section class="tabs">

    <div class="tabs__tab-wrapper">
      <div v-for="tab in tabList" :key="tab" @click="activeTab = tab" :class="['tabs__tab', {'tabs__tab--active': activeTab == tab}]">
        <p class="tabs__tab-title">{{ tab }}</p>
      </div>
    </div>

    <div class="tabs__tab-content">
      <BasicComparison v-show="activeTab == 'Stats'" :pick1="pick1" :pick2="pick2" />
      <p v-show="activeTab == 'Reviews'">Reviews</p>
      <p v-show="activeTab == 'Description' && activeProduct == 'pick1'" v-html="pick1.description" class="tabs__tab-description"></p>
      <p v-show="activeTab == 'Description' && activeProduct == 'pick2'" v-html="pick2.description" class="tabs__tab-description"></p>
      <p v-show="activeTab == 'Other Info'">Other Info</p>
    </div>

  </section>
</template>

<script>
import BasicComparison from '@/components/BasicComparison.vue'

export default {
  name: 'ComparisonTabs',

  components: {
    BasicComparison
  },

  props: {
    pick1: {
      type: Object,
      required: true
    },
    pick2: {
      type: Object,
      required: true
    }
  },

  data() {
    return {
      tabList: ["Stats", "Description", "Other Info", "Reviews"],
      activeTab: 'Stats',
      activeProduct: 'pick1'
    }
  }
}
</script>

<style lang="scss">

  .tabs {

    &__tab-wrapper {
      display: flex;
      align-items: flex-end;
    }

    &__tab {
      width: 25%;
      height: 32px;
      display: flex;
      justify-content: center;
      background-color: #e8e8e8;
      font-size: 0.7em;
      text-transform: uppercase;
      font-weight: bold;
      border-top-left-radius: 6px;
      border-top-right-radius: 6px;

      &--active {
        height: 48px;
        background-color: #0f0;
      }
    }
    
    &__tab-title {
      margin: auto;
    }

    &__tab-content {
      border: 1px #e8e8e8 solid;
      border-top: none;
      border-bottom-left-radius: 6px;
      border-bottom-right-radius: 6px;
    }

    &__tab-description {
      padding: 16px;
      text-align: left;
    }
  }

</style>