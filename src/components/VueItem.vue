<template>
  <li>
    <img style="width: 25px; height: 25px" :src="twit.avatar" alt="1" />
    {{ twit.body }} - {{ twit.data }}
  </li>
  <!-- <p>{{ title }}</p> -->
</template>

<script>
export default {
  props: {
    twit: {
      type: String,
      default: "Hello Dori",
    },
  },
};
</script>
