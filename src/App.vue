<template>
  <div style="position: fixed;">
    <app-header></app-header>
    <app-background></app-background>
  </div>
</template>
<script>
import AppBackground from "@/components/AppBackground";
import AppHeader from "@/components/AppHeader";
export default {
  components: {
    AppBackground,
    AppHeader,
  },
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
</style>
