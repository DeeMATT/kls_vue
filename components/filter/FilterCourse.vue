<template>
  <div>
    <h5 class="title mb-6">Filter</h5>
    <p class="sub-title mb-4">Difficulty</p>
    <ul>
      <li>
        <span>Beginner</span>
        <input type="checkbox" v-model="difficulty" value="beginner" />
      </li>
      <li>
        <span>Intermediate</span>
        <input type="checkbox" v-model="difficulty" value="intermediate" />
      </li>
      <li>
        <span>Advanced</span>
        <input type="checkbox" v-model="difficulty" value="advanced" />
      </li>
      <li>
        <span>All</span>
        <input type="checkbox" v-model="difficulty" value="all" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    difficulty: [],
  }),
}
</script>

<style scoped>
.title {
  @apply flex-grow text-xl font-semibold text-gray-600;
}
.sub-title {
  @apply text-gray-800 font-semibold;
}
ul > li > input {
  /* display: none; */
  float: right;
}
</style>
