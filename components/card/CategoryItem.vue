<template>
  <a
    class="bg-white rounded-lg border border-gray-300 shadow-hover p-6 pb-12 relative"
  >
    <span class="inline-block bg-gray-100 w-16 h-16 rounded-lg"></span>
    <p class="prose-2xl text-orange-500 font-semibold my-3">
      {{ category.name }}
    </p>
    <p>{{ category.desc }}</p>
    <div class="absolute text-center bottom-0 mb-5">
      <nuxt-link to="/" class="text-black text-sm inline-block"> View more </nuxt-link>
    </div>
  </a>
</template>

<script>
export default {
  props: {
    category: { type: Object, required: true },
  }
}
</script>

<style scoped>
.shadow-hover:hover {
  box-shadow: 0 10px 36px rgba(249, 158, 66, 0.16);
}
.view-more {
  @apply bg-white;
}
</style>
