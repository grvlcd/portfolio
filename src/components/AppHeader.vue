<template lang="">
  <nav
    :class="{ fillNav: toggleNav }"
    class="text-white bg-black bg-opacity-40"
  >
    <div class="w-screen px-4 mx-auto ">
      <div
        class="flex flex-row items-center justify-between px-4 py-3 text-2xl "
      >
        <div class="flex items-center px-3 py-1 space-x-2">
          <a href="#">
            <svg
              class=" w-14 h-14"
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
        <div class="hidden md:flex">
          <a href="#" class="px-2 py-1 rounded-md hover:bg-pink-300">Blogs</a>
          <a href="#" class="px-2 py-1 rounded-md hover:bg-pink-300">About</a>
          <a href="#" class="px-2 py-1 rounded-md hover:bg-pink-300"
            >Portfolio</a
          >
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
      class="fixed flex flex-col items-stretch w-full text-2xl bg-black bg-opacity-40 md:hidden"
    >
      <a
        class="block py-2 bg-opacity-50 px-7 hover:bg-pink-200 hover:text-black"
        href="#"
        >Blogs</a
      >

      <a
        class="block py-2 bg-opacity-50 px-7 hover:bg-pink-200 hover:text-black"
        href="#"
        >Portfolio</a
      >

      <a
        class="block py-2 bg-opacity-50 px-7 hover:bg-pink-200 hover:text-black"
        href="#"
        >About</a
      >
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
