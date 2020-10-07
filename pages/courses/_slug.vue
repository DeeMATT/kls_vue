<template>
  <div class="min-h-screen mb-24">
    <section class="bg-orange-100">
      <div class="container mx-auto pt-20 pb-24">
        <course-view-banner :course="course" />
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <div class="grid lg:grid-cols-12 gap-6">
          <div class="col-span-3">
            <h5 class="title mb-5">Curriculum</h5>
            <div class="mb-8">
              <h6 class="text-md text-gray-800 font-bold mb-5">
                Part 1 - Understanding Money
              </h6>
              <ul class="part-list">
                <li class="mb-4">
                  <nuxt-link to="/"
                    >Understanding the concept of money</nuxt-link
                  >
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Career vs business (or both?) </nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Finding new income sources</nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Starting a business</nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Residual income sources</nuxt-link>
                </li>
              </ul>
            </div>
            <div class="mb-8">
              <h6 class="text-md text-gray-800 font-bold mb-5">
                Part 2 - Creating income
              </h6>
              <ul class="part-list">
                <li class="mb-4">
                  <nuxt-link to="/"
                    >Understanding the concept of money</nuxt-link
                  >
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Career vs business (or both?) </nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Finding new income sources</nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Starting a business</nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Residual income sources</nuxt-link>
                </li>
              </ul>
            </div>
            <div class="mb-8">
              <h6 class="text-md text-gray-800 font-bold mb-5">
                Part 2 - Creating income
              </h6>
              <ul class="part-list">
                <li class="mb-4">
                  <nuxt-link to="/"
                    >Part 3 - Maximizing profits, minimizing stress</nuxt-link
                  >
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Career vs business (or both?) </nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Finding new income sources</nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Starting a business</nuxt-link>
                </li>
                <li class="mb-4">
                  <nuxt-link to="/">Residual income sources</nuxt-link>
                </li>
              </ul>
            </div>
          </div>
          <div class="col-span-9">
            <div>
              <h5 class="mb-8">Introduction</h5>
              <video-frame class="mb-8" />
            </div>
            <div>
              <h5 class="mb-8">Part 1 - Understanding Money</h5>
            </div>
            <items-section-group title="320 Courses">
              <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5">
                <course-item
                  v-for="(course, key) in courses"
                  :key="key"
                  :course="course"
                />
              </div>
            </items-section-group>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-20">
        <telegram-community-section />
      </div>
    </section>
  </div>
</template>

<script>
import Vue from 'vue'

const courses = require('@/static/json/latest-courses.json')

export default {
  fetch({ store }) {
    store.commit('app/SET_DARK_MENU', true)
  },
  data: () => ({
    home: 'home',
    tags: [
      'Bitcoin',
      'Agriculture',
      'Fashion design',
      'Development',
      'Business',
    ],
    course: courses[0],
    courses: _.take(courses, 3),
  }),
}
</script>

<style scoped>
h5 {
  @apply flex-grow text-xl font-semibold text-gray-600;
}
.part-list {
  @apply border-gray-200 border-b;
  @apply text-sm text-gray-700;
}
</style>
