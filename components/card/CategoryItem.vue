<template>
  <div class="bg-white rounded-lg border border-gray-300 shadow-hover relative">
    <div class="p-6 pb-20">
      <span class="inline-block bg-gray-100 w-16 h-16 rounded-lg"></span>
      <p
        class="text-2xl text-orange-500 font-semibold my-5"
        style="line-height: normal"
      >
        {{ category.name }}
      </p>
      <p class="text-sm text-gray-700">{{ category.desc }}</p>
    </div>
    <div class="absolute text-center bottom-0 mb-5 w-full">
      <nuxt-link to="/" class="view-more text-black text-sm inline-block">
        View more
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    category: { type: Object, required: true },
  },
}
</script>
