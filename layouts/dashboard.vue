<template>
  <div class="layout">
    <Sidebar />
    <div class="content-wrapper dashboard px-lg-5 px-md-4 px-3">
      <DashNavbar />
      <div class="container mx-auto px-0 mt-8 mb-5">
        <Nuxt />
        <DashFooter />
      </div>
    </div>
  </div>
</template>

<style scoped>
.layout {
  background: #fcf8f7;
}
</style>