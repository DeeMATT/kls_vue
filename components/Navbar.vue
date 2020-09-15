<template>
  <div class="container mx-auto">
    <nav class="flex items-center justify-between flex-wrap py-6">
      <div class="flex items-center flex-shrink-0 mr-6">
        <img src="/logo.svg" />
      </div>
      <div class="block lg:hidden">
        <button
          @click="toggleMenu"
          class="flex items-center px-3 py-2 border rounded text-gray-700 border-gray-900"
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
      <div
        :class="{ hidden: !open }"
        class="w-full block flex-grow lg:flex lg:items-center lg:w-auto"
      >
        <div class="mx-auto">
          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block lg:mt-0 text-black hover:text-orange-500 mr-4"
          >
            Courses
          </a>
          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block lg:mt-0 text-black hover:text-orange-500 mr-4"
          >
            Webinars
          </a>
          <a
            href="#responsive-header"
            class="block mt-4 lg:inline-block lg:mt-0 text-black hover:text-orange-500"
          >
            Blog
          </a>
        </div>
        <div>
          <router-link to="/login" class="lg:mr-4 font-semibold"> Log In </router-link>
          <router-link to="/signup" class="signup-btn lg:mt-0"
            >Sign Up</router-link
          >
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  data: () => ({
    open: false,
  }),
  methods: {
    toggleMenu() {
      this.open = !this.open
    }
  },
}
</script>

<style scoped>
.signup-btn {
  @apply inline-block px-4 py-3 leading-none border rounded-md font-semibold;
  @apply bg-orange-500 text-white;
}
.signup-btn:hover {
  @apply bg-orange-600;
}
</style>
