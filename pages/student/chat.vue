<template>
  <div class="mb-20">
    <section class="bg-orange-100">
      <div class="container mx-auto mb-10 px-4 lg:px-0">
        <div class="md:grid grid-cols-12 gap-5">
          <div class="col-span-3 max-h-content-screen mb-8 lg:mb-0">
            <chat-contacts />
          </div>
          <div class="col-span-6 max-h-content-screen mb-8 lg:mb-0">
            <chat-window />
          </div>
          <div class="col-span-3 max-h-content-screen">
            <chat-members />
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Vue from 'vue'

const webinars = require('@/static/json/webinars.json')

export default {
  layout: 'dashboard',
  fetch({ store }) {
    store.commit('app/SET_TITLE', 'Chat')
  },
  data: () => ({
    webinars: _.take(webinars, 4),
    undoneTasks: _.take(webinars, 3),
  }),
}
</script>
