<template>
  <form @submit.prevent="onSubmit">
    <textarea v-model="body" required placeholder="Type tweet here" />
    <br />
    <button class="btn btnTweet" type="submit">Post Tweet</button>
  </form>
</template>

<script>
// COMPOSITION API
import { ref } from "vue";

export default {
  emits: ["onSubmit"],

  setup(_, { emit }) {
    const body = ref("");

    const onSubmit = () => {
      emit("onSubmit", {
        id: Math.round(Math.random() * 30),
        avatar: `https://avatars.dicebear.com/api/male/${Date.now()}.svg`,
        body: body.value,
        date: new Date(Date.now()).toLocaleString(),
        likes: 0,
      });
      body.value = "";
    };

    return {
      body,
      onSubmit,
    };
  },
};
// Options API
// export default {
//   data() {
//     return {
//       body: "",
//     };
//   },
//   methods: {
//     onSubmit() {
//       this.$emit("onSubmit", {
//         id: Math.round(Math.random() * 30),
//         avatar: `https://avatars.dicebear.com/api/male/${Date.now()}.svg`,
//         body: this.body,
//         data: new Date(Date.now()).toLocaleString(),
//         likes: 0,
//       });
//       this.body = "";
//     },
//   },
// };
</script>
