<template>
  <div class="min-h-screen mb-24">
    <section class="bg-orange-100">
      <div class="container mx-auto">
        <h2 class="title text-4xl md:text-5xl font-bold md:pt-10 pt-8 mb-8">
          Webinars
        </h2>
        <div class="grid grid-cols-2 gap-32">
          <div class="col-span-2 md:col-span-1 px-4 lg:px-0">
            <search-box />
            <div class="mt-8 mb-6 lg:mb-32">
              <span class="text-xs text-gray-700 block mb-4"
                >Popular webinar searches</span
              >
              <tags-slider :tags="tags" />
            </div>
          </div>
          <div class="col-span-2 md:col-span-1 px-4 lg:px-0">
            <p class="text-md md:text-xl mb-8" style="line-height: unset">
              Learn from many experts and acquire knowledge that will put you in
              the top 3% of your field. Start your journey now.
            </p>
            <button class="btn btn-primary">Create Webinar</button>
          </div>
        </div>
      </div>
    </section>
    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <div class="grid grid-cols-12 gap-4">
          <div class="col-span-2">
            <filter-webinar />
          </div>
          <div class="col-span-10 lg:ml-24">
            <items-section-group title="210 Webinars">
              <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-5">
                <webinar-item
                  v-for="(webinar, key) in webinars"
                  :key="key"
                  :webinar="webinar"
                />
              </div>
            </items-section-group>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Vue from 'vue'

const tags = require('@/static/json/tags-courses.json')
const webinars = require('@/static/json/webinars.json')

export default {
  fetch({ store }) {
    store.commit('app/SET_DARK_MENU', true)
  },
  data: () => ({
    home: 'home',
    tags,
    webinars,
  }),
}
</script>
