<template lang="">
  <nav :class="{ fillNav: toggleNav }">
    <div class="w-screen px-4 mx-auto">
      <div
        class="flex flex-row items-center justify-between px-4 py-3 text-2xl"
      >
        <div class="flex items-center px-3 py-1 space-x-2">
          <a href="#">
            <svg
              class="text-gray-800 w-14 h-14"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4"
              />
            </svg>
          </a>
          <h1 class="hidden text-2xl md:flex">Developed by Christian</h1>
        </div>
        <div class="hidden space-x-5 md:flex">
          <a href="#">Blogs</a>
          <a href="#">About</a>
          <a href="#">Portfolio</a>
        </div>

        <!-- Hamburger Menu-->
        <div class="flex items-center md:hidden">
          <button v-on:click="showMenu">
            <svg
              class="w-10 h-10"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>
    <!-- Mobile Nav -->
    <div
      v-if="toggleNav"
      class="flex flex-col border-black  items-stretch text-2xl border-b-2 text-right #fc92c6"
    >
      <a class="block py-2 px-7 hover:bg-gray-300" href="#">Blogs</a>

      <a class="block py-2 px-7 hover:bg-gray-300" href="#">Portfolio</a>

      <a class="block py-2 px-7 hover:bg-gray-300" href="#">About</a>
    </div>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      toggleNav: false,
    };
  },
  methods: {
    showMenu() {
      this.toggleNav = !this.toggleNav;
    },
  },
};
</script>
<style>
.fillNav {
  background-color: #fc92c6;
}
</style>
