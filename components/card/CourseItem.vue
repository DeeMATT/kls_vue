<template>
  <nuxt-link
    :to="'/courses/' + course.slug"
    class="block bg-white rounded-lg border border-gray-300 shadow-hover relative pb-12"
  >
    <div class="absolute mt-3 ml-3">
      <span class="top-tag">Course</span>
    </div>
    <div class="item-img">
      <img class="block min-w-full" src="/card/course.jpg" />
    </div>
    <div class="p-6">
      <p class="text-md text-gray-900 font-semibold mb-0">
        {{ course.name }}
      </p>
      <p class="text-sm text-gray-700">{{ course.author }}</p>
    </div>
    <div class="absolute grid grid-cols-2 w-full bottom-0 mb-5">
      <div class="pl-5">
        <rating :grade="3" :max-stars="5" />
      </div>
      <div class="text-sm text-gray-700 text-right pr-5">56 ratings</div>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    course: { type: Object, required: true },
  }
}
</script>

<style scoped>
.top-tag {
  background-color: rgba(0, 0, 0, 0.25);
  padding: 4px 20px 4px 8px;
  font-size: 12px;
  line-height: 22px;
  color: #fff;
  border-radius: 12px;
  position: relative;
}
.top-tag::after {
  content: '';
  display: inline-block;
  border-radius: 4px;
  width: 8px;
  height: 8px;
  right: 6px;
  top: 8px;
  background: #0797ce;
  position: absolute;
}
</style>
