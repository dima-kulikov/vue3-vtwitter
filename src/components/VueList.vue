<template>
  <select v-model="sortBy">
    <option value="data">Sort by date</option>
    <option value="likes">Sort by Like</option>
  </select>
  <p>{{ sortBy }}</p>
  <ul class="tweets__wrapper">
    <VueItem v-for="item in items" :key="item.id" :item="item" />
  </ul>
</template>


<script>
import { ref } from "vue";
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
  setup() {
    const sortBy = ref("date");

    return {
      sortBy,
    };
  },
};
</script>

<style>
</style>