<template>
  <Landing/>
  <!-- <router-view/> -->
</template>

<script lang="ts">
import { defineComponent } from "@vue/runtime-core";
import Landing from "./views/Landing.vue";

export default defineComponent({
  components: {
    Landing,
  }
})
</script>

<style>

</style>