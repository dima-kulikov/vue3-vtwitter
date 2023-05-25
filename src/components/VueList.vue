<template>
  <ul>
    <VueItem v-for="twit in items" :key="twit.id" :twit="twit" />
  </ul>
</template>


<script>
import VueItem from "@/components/VueItem.vue";
export default {
  components: {
    VueItem,
  },
  data() {
    return {
      lesia: "helllo",
      items: [
        {
          id: 1,
          likes: 1,
          body: "hello vue3",
          avatar: "https://avatars.dicebear.com/api/male/343.svg",
          data: new Date(Date.now()).toLocaleString(),
        },
      ],
    };
  },
  methods: {
    pushItem() {
      this.items.push({
        id: this.items.length + 1,
        avatar: `https://avatars.dicebear.com/api/male/${Date.now()}.svg`,
        body: this.item,
        data: new Date(Date.now()).toLocaleString(),
      });
      this.item = "";
    },
  },
};
</script>

<style>
</style>