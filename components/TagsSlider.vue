<template>
  <div class="block">
    <span
      v-for="(tag, key) in tags"
      :key="key"
      :class="'bg-' + color + '-500' + ' bg-opacity-' + opacity"
      class="py-2 px-4 text-xs text-gray-900 rounded-full mr-3 inline-block cursor-pointer"
      >{{ tag }}</span
    >
  </div>
</template>

<script>
export default {
  props: {
    tags: { type: Array, required: true },
    color: { type: String, default: 'orange' },
    opacity: { type: Number, default: 25 },
  },
}
</script>
