<template>
  <div class="rounded-lg p-16" :class="bg">
    <img v-if="icon" :src="icon" class="inline-block mb-8" />
    <h3
      class="text-4xl font-semibold mb-5"
      :class="dark ? 'text-white' : 'text-black'"
    >
      {{ title }}
    </h3>
    <p class="text-sm mb-5" :class="dark ? 'text-white' : 'text-black'">
      {{ desc }}
    </p>
    <nuxt-link
      v-if="linkUrl"
      :to="linkUrl"
      :class="dark ? 'text-white light' : 'text-black'"
      class="view-more text-sm"
    >
      {{ linkText }}
    </nuxt-link>
  </div>
</template>

<script>
export default {
  props: {
    icon: { type: String, required: true },
    title: { type: String, required: true },
    desc: { type: String, required: true },
    linkUrl: { type: String, default: '/' },
    linkText: { type: String, default: 'See more' },
    bg: { type: String, default: 'bg-gray-200' },
    dark: { type: Boolean, default: false },
  },
}
</script>

<style scoped>
.view-more {
  display: inline-block;
  background: url('/actions/arrow-right.svg');
  background-repeat: no-repeat;
  background-position: right 0 top 3px;
  padding: 0 20px 0 0;
}
.view-more.light {
  background-image: url('/actions/arrow-right-light.svg');
}
</style>
