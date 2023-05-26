<template>
  <ul class="tweets__wrapper">
    <VueItem v-for="item in items" :key="item.id" :item="item" />
  </ul>
</template>


<script>
import VueItem from "@/components/VueItem.vue";
export default {
  props: {
    items: {
      type: Array,
      reqired: true,
    },
  },
  components: {
    VueItem,
  },
};
</script>

<style>
</style>