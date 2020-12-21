<template>
  <div class="flex flex-row progress">
    <div class="progress-bar" :style="{ width: `${percentage}%` }"></div>
  </div>
</template>

<script>
export default {
  props: {
    percentage: { type: Number, default: 10 },
  },
}
</script>

<style scoped>
.progress {
  height: 6px;
  background: rgba(249, 158, 66, 0.16);
  border-radius: 4px;
}
.progress-bar {
  height: 6px;
  background: #f99e42;
  border-radius: 4px;
}
</style>
