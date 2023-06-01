<template>
  <div class="wrapper">
    <!-- header -->
    <div class="wrapper-content">
      <div class="view">
        <div class="container">
          <VueForm @onSubmit="handleSubmit" />
          <VueList :items="items" />
        </div>
      </div>
    </div>
    <!-- footer -->
  </div>
</template>


<script>
import { ref } from "vue";
import VueList from "@/components/VueList.vue";
import VueForm from "@/components/VueForm.vue";

// COMPOSITION API
export default {
  components: {
    VueList,
    VueForm,
  },
  setup() {
    const items = ref([
      {
        id: 1,
        likes: 1,
        body: "Toha 23",
        avatar: "https://avatars.dicebear.com/api/male/343.svg",
        date: new Date(Date.now()).toLocaleString(),
      },
      {
        id: 2,
        likes: 3,
        body: "Happy bee",
        avatar: "https://avatars.dicebear.com/api/male/34d3.svg",
        date: new Date(Date.now()).toLocaleString(),
      },
      {
        id: 3,
        likes: 7,
        body: "Hot Summer",
        avatar: "https://avatars.dicebear.com/api/male/3иd3.svg",
        date: new Date(Date.now()).toLocaleString(),
      },
    ]);
    function handleSubmit(item) {
      items.value.push(item);
    }

    return {
      items,
      handleSubmit,
    };
  },
};
// Options API
// export default {
//   components: {
//     VueList,
//     VueForm,
//   },
//   data() {
//     return {
//       items: [
//         {
//           id: 1,
//           likes: 1,
//           body: "hello vue3",
//           avatar: "https://avatars.dicebear.com/api/male/343.svg",
//           data: new Date(Date.now()).toLocaleString(),
//         },
//       ],
//     };
//   },
//   methods: {
//     handleSubmit(item) {
//       this.items.push(item);
//     },
//   },
// };
</script>

<style>
</style>
// https://www.youtube.com/watch?v=UFtRD4JA_Es&list=PLkCrmfIT6LBRcU37KZnMqy5hcTuwRhQkb&index=3

