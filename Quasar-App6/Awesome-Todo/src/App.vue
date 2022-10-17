<template>
  <div id="q-app">
    <router-view />
  </div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
});
</script>

<style>
 .text-strikethrough {
  text-decoration: line-through;
 }
</style>
