<template>
  <div class="bg-none">
    <div class="flex">
      <h5
        v-if="title"
        class="flex-grow prose-xl font-semibold text-gray-600 mb-6"
      >
        {{ title }}
      </h5>
      <nuxt-link v-if="more" :to="more" class="hover:text-orange-500">
        {{ 'See more' }}
      </nuxt-link>
    </div>
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    title: { type: String, required: true },
    more: { type: String, required: false },
  },
}
</script>

<style scoped>
.view-more {
  @apply bg-white;
}
</style>
