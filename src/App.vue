<template>
  <div class="wrapper">
    <!-- header -->
    <div class="wrapper-content">
      <div class="view">
        <div class="container">
          <VueList />
        </div>
      </div>
    </div>
    <!-- footer -->
  </div>
</template>


<script>
import VueList from "@/components/VueList.vue";
export default {
  components: {
    VueList,
  },
};
</script>

<style>
</style>


