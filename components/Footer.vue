<template>
  <section>
    <div class="container mx-auto px-4 lg:px-0">
      <div class="grid grid-cols-12 py-12">
        <div class="col-span-6 md:col-span-3 mb-8 md:mb-0">
          <img src="/logo.svg" />
        </div>
        <div class="col-span-12 md:col-span-5">
          <div class="grid grid-cols-12 text-sm mb-10 md:mb-0">
            <div class="col-span-5 md:col-span-3 mb-8 md:mb-0">
              <strong class="block font-semibold mb-3">Links</strong>
              <ul>
                <li><nuxt-link to="/">Courses</nuxt-link></li>
                <li><nuxt-link to="/">Webinars</nuxt-link></li>
                <li><nuxt-link to="/">Blogs</nuxt-link></li>
              </ul>
            </div>
            <div class="col-span-7 md:col-span-5 mb-8 md:mb-0">
              <strong class="block font-semibold mb-3">Register</strong>
              <ul>
                <li><nuxt-link to="/">Become an instructor</nuxt-link></li>
                <li><nuxt-link to="/">Become a student</nuxt-link></li>
              </ul>
            </div>
            <div class="col-span-12 md:col-span-4">
              <strong class="block font-semibold mb-3">Resources</strong>
              <ul>
                <li><nuxt-link to="/">Privacy Policy</nuxt-link></li>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-span-12 md:col-span-4">
          <p class="mb-0">
            <small class="text-xs">
              The leading online learning platform for hands on learning
              experiences focused on capacity building and skill acquisition
              relevant for today’s economy. Klasroom provides access to seasoned
              industry experts to learners willing to implement tried and tested
              strategies at their own pace and budget.
            </small>
          </p>
        </div>
      </div>
      <div class="pb-5 text-center">
        <hr class="mb-4" />
        <small class="text-xs">© 2020 Klasroom . All Rights Reserved.</small>
      </div>
      <!-- <nav class="flex items-center justify-between flex-wrap py-6">
        <div class="flex items-center flex-shrink-0 mr-6">
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
      </nav> -->
    </div>
  </section>
</template>

<script>
export default {
  data: () => ({
    open: false,
  }),
  methods: {
    toggleMenu() {
      this.open = !this.open
    },
  },
}
</script>

<style scoped>
section {
  background-color: #fcf8f7;
}
li {
  line-height: 30px;
}
</style>
