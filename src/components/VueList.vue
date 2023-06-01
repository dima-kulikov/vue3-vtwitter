<template>
  <select v-model="sortBy">
    <option value="date">Sort by date</option>
    <option value="likes">Sort by Like</option>
  </select>
  <!-- <p>{{ sortBy }}</p> -->
  <ul class="tweets__wrapper">
    <VueItem
      v-for="item in sorteredItems"
      :key="item.id"
      :item="item"
      @upLikes="upLikesDone"
    />
  </ul>
</template>


<script>
import { ref, computed } from "vue";
import VueItem from "@/components/VueItem.vue";

export default {
  components: { VueItem },
  props: {
    items: {
      type: Array,
      reqired: true,
    },
  },
  setup(props) {
    const sortBy = ref("date");

    const sorteredItems = computed(() => {
      let aut = props.items;
      return aut.sort((a, b) => {
        if (a[sortBy.value] > b[sortBy.value]) return -1;
        // if (a[sortBy.value] < b[sortBy.value]) return 1;
      });
    });
    function upLikesDone(item) {
      let bigLikes = sorteredItems.value.find((el) => el.id === item);
      bigLikes.likes += 1;
    }
    return {
      sortBy,
      sorteredItems,
      upLikesDone,
    };
  },
};
</script>

<style>
</style>