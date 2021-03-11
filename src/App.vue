<template>
  <div style="position: fixed;">
    <app-header></app-header>
    <app-background></app-background>
    <div id="main">
      <app-hero></app-hero>
    </div>
  </div>
</template>
<script>
import AppBackground from "@/components/AppBackground";
import AppHeader from "@/components/AppHeader";
import AppHero from "@/components/AppHero";
export default {
  components: {
    AppBackground,
    AppHeader,
    AppHero,
  },
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
</style>
