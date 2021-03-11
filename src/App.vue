<template>
  <div style="position: fixed;">
    <div class="w-screen h-32 ">
      <ul class="flex flex-row justify-end p-3 text-2xl">
        <li>About</li>
        <li>Blogs</li>
        <li>Projects</li>
      </ul>
    </div>
    <app-background></app-background>
  </div>
</template>
<script>
import AppBackground from "@/components/AppBackground";
export default {
  components: {
    AppBackground,
  },
};
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
</style>
