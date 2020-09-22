<template>
  <div :class="{ 'bg-orange-100': darkMenu }">
    <div class="container mx-auto">
      <nav class="flex items-center justify-between flex-wrap py-4 md:py-6">
        <nuxt-link
          to="/"
          class="flex items-center flex-shrink-0 mr-6 ml-4 lg:ml-0"
        >
          <img src="/logo.svg" />
        </nuxt-link>
        <div class="block lg:hidden mr-4 lg:mr-0">
          <button
            class="flex items-center px-3 py-2 border rounded text-gray-700 border-gray-900"
            @click="toggleMenu"
          >
            <svg
              class="fill-current h-3 w-3"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Menu</title>
              <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
            </svg>
          </button>
        </div>
        <div :class="{ hidden: !open }" class="menu-group">
          <div class="mx-auto">
            <nuxt-link
              to="/courses"
              class="block mt-4 lg:inline-block lg:mt-0 text-black hover:text-orange-500 mr-4"
            >
              Courses
            </nuxt-link>
            <nuxt-link
              to="/webinars"
              class="block mt-4 lg:inline-block lg:mt-0 text-black hover:text-orange-500 mr-4"
            >
              Webinars
            </nuxt-link>
            <nuxt-link
              to="/blog"
              class="block mt-4 lg:inline-block lg:mt-0 text-black hover:text-orange-500"
            >
              Blog
            </nuxt-link>
          </div>
          <div class="mt-8 md:mt-0 mb-6 md:mb-0">
            <router-link
              to="/login"
              class="btn lg:mr-4 bg-blue-400 text-white md:text-black md:bg-transparent block md:inline-block text-center mb-5 md:mb-0"
            >
              Log In
            </router-link>
            <router-link
              to="/signup"
              class="btn btn-primary lg:mt-0 block md:inline-block text-center"
              >Sign Up</router-link
            >
          </div>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data: () => ({
    open: false,
  }),
  computed: {
    ...mapState({
      darkMenu: (state) => state.app.darkMenu,
    }),
  },
  methods: {
    toggleMenu() {
      this.open = !this.open
    },
  },
}
</script>

<style scoped>
.menu-group {
  @apply transition duration-500;
  @apply w-full flex-grow bg-white mt-5 shadow-lg px-4;
}
@media (min-width: 768px) {
  .menu-group {
    @apply flex items-center w-auto shadow-none;
    @apply bg-transparent px-0 mt-0;
  }
}
</style>
