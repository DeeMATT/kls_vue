<template>
  <div
    class="flex flex-row rounded-xl bg-white border border-gray-300 divide-x divide-gray-300"
  >
    <div class="flex flex-col mr-auto my-auto text-gray-700 py-6 px-5">
      <span class="block text-xs font-semibold">{{ name }}</span>
    </div>
    <button class="text-sm py-4 px-5 pl-10 text-gray-700 focus:outline-none">
      Download
    </button>
  </div>
</template>

<script>
export default {
  props: {
    name: { type: String, required: true },
    link: { type: String, required: true },
  },
}
</script>

<style scoped>
button {
  width: 144px;
  background-image: url('/icon/download.svg');
  background-repeat: no-repeat;
  background-position: top 50% left 15px;
}
</style>
