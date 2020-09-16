<template>
  <div class="bg-none">
    <div class="flex mb-5">
      <h5 v-if="title" class="flex-grow text-xl font-semibold text-gray-600">
        {{ title }}
      </h5>
      <nuxt-link
        v-if="more"
        :to="more"
        class="view-more hover:text-orange-500 text-black text-sm inline-block mt-2"
      >
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
  display: inline-block;
  background: url('/actions/arrow-right.svg');
  background-repeat: no-repeat;
  background-position: right 0 top 3px;
  padding: 0 20px 0 0;
}
</style>
