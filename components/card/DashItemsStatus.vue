<template>
  <div class="bg-white rounded-xl border border-gray-300 shadow-hover relative">
    <div class="p-4 md:p-5 lg:p-6 pb-16 md:pb-18 lg:pb-20">
      <h4 class="text-gray-700 font-extrabold leading-snug mt-0 md:mt-5 mb-4">
        {{ title }}
      </h4>
      <div class="mb-8">
        <p class="text-xs md:text-sm text-gray-700">{{ undone }}</p>
        <p class="text-xs md:text-sm text-gray-700">{{ done }}</p>
      </div>
      <div>
        <span
          v-for="(item, key) in items"
          :key="key"
          class="course-stacks mr-3"
        ></span>
      </div>
    </div>
    <div v-if="more" class="absolute md:text-center bottom-0 mb-5 w-full px-5">
      <nuxt-link :to="more" class="text-gray-700 inline-block">
        <span class="text-xs">See more</span>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: { type: String, required: true },
    items: { type: Array, required: true },
    done: { type: String, required: true },
    undone: { type: String, required: true },
    more: { type: String, default: null },
  },
}
</script>

<style scoped>
.course-stacks {
  display: inline-block;
  width: 52px;
  height: 52px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  border-radius: 12px;
  @apply bg-gray-300;
}
@media (max-width: 640px) {
  h4 {
    @apply text-base;
  }
}
</style>
