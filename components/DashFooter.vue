<template>
  <section>
    <div class="container mx-auto px-4 lg:px-0">
      <div class="pb-5 text-center">
        <hr class="mb-4 border-gray-300" />
        <small class="text-xs">© 2020 Klasroom. All Rights Reserved.</small>
      </div>
    </div>
    <login-modal />
    <forgot-password-modal />
    <reset-password-modal />
    <purchase-modal />
    <notice-modal />
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
  background-color: transparent;
}
</style>
