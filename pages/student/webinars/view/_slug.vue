<template>
  <div class="min-h-screen mb-24">
    <section class="bg-orange-100">
      <div class="container mx-auto mb-10 px-4 lg:px-0">
        <div class="grid grid-cols-12 gap-5">
          <div
            v-if="!$device.isMobile"
            class="col-span-full lg:col-span-8 xl:col-span-8"
          >
            <div
              class="bg-white rounded-xl border border-gray-300 shadow-hover overflow-hidden relative"
            >
              <webinar-video-frame
                status="countdown"
                class="rounded-b-none mb-4"
              />
              <div class="px-4 md:px-5 lg:px-6 py-4">
                <div class="pb-10 md:pb-16">
                  <h5 class="font-bold mb-3 leading-tight text-gray-700">
                    The Cryptocurrency Masterclass
                  </h5>
                  <p class="text-xs mb-4 text-gray-700 leading-normal">
                    Everything you need to know about Cryptocurrency and ways
                    you can profit from it
                  </p>
                  <div class="flex mb-4">
                    <img src="/avatar.jpg" class="rounded-full mr-3 w-8 h-8" />
                    <span class="text-xs text-gray-700 block my-auto">
                      Joy Adeleke</span
                    >
                    <ul class="social-icons with-avatar my-auto">
                      <li class="twitter">
                        <a href="#"></a>
                      </li>
                      <li class="share">
                        <a href="#"></a>
                      </li>
                    </ul>
                  </div>
                  <hr class="-mx-4 md:-mx-5 lg:-mx-6" />
                  <div class="flex flex-row gap-4 text-gray-700 mt-5">
                    <span class="text-base font-semibold my-auto"
                      >Starting a business</span
                    >
                    <span class="text-xs my-auto">Part 1, Lesson 4</span>
                  </div>
                  <p class="text-xs mt-4 text-gray-700 leading-normal">
                    Anyone who lived in the time of legends such as Henry Ford,
                    Alexander Graham Bell, Thomas Edison and Albert Einstein
                    could be forgiven for thinking everything that can be
                    invented already has been invented. Of course, if we’d
                    stopped there, we wouldn’t have the computer or the
                    internet. The past century of our history stands as a
                    testament to human ingenuity and our persistence to make
                    things better.
                  </p>
                </div>
              </div>
            </div>
          </div>
          <div class="col-span-full lg:col-span-4 xl:col-span-4">
            <div
              class="flex flex-col flex-1 bg-white rounded-xl border border-gray-300 min-h-content-screen"
            >
              <tabs-menu v-model="tab" :tabs="tabs" />
              <div v-if="$device.isMobile && tab === 0 && tabs.length === 5">
                <webinar-video-frame
                  status="countdown"
                  class="rounded-b-none mb-4"
                />
                <div class="px-4 md:px-5 lg:px-6 py-4">
                  <div class="pb-10 md:pb-16">
                    <h5 class="font-bold mb-3 leading-tight text-gray-700">
                      The Cryptocurrency Masterclass
                    </h5>
                    <p class="text-xs mb-4 text-gray-700 leading-normal">
                      Everything you need to know about Cryptocurrency and ways
                      you can profit from it
                    </p>
                    <div class="flex mb-4">
                      <img
                        src="/avatar.jpg"
                        class="rounded-full mr-3 w-8 h-8"
                      />
                      <span class="text-xs text-gray-700 block my-auto">
                        Joy Adeleke</span
                      >
                      <ul class="social-icons with-avatar my-auto">
                        <li class="twitter">
                          <a href="#"></a>
                        </li>
                        <li class="share">
                          <a href="#"></a>
                        </li>
                      </ul>
                    </div>
                    <hr class="-mx-4 md:-mx-5 lg:-mx-6" />
                    <div class="flex flex-row gap-4 text-gray-700 mt-5">
                      <span class="text-base font-semibold my-auto"
                        >Starting a business</span
                      >
                      <span class="text-xs my-auto">Part 1, Lesson 4</span>
                    </div>
                    <p class="text-xs mt-4 text-gray-700 leading-normal">
                      Anyone who lived in the time of legends such as Henry
                      Ford, Alexander Graham Bell, Thomas Edison and Albert
                      Einstein could be forgiven for thinking everything that
                      can be invented already has been invented. Of course, if
                      we’d stopped there, we wouldn’t have the computer or the
                      internet. The past century of our history stands as a
                      testament to human ingenuity and our persistence to make
                      things better.
                    </p>
                  </div>
                </div>
              </div>
              <div
                v-if="
                  (tab === 0 && tabs.length === 4) ||
                  (tab === 1 && tabs.length === 5)
                "
              >
                <chat-messages no-card />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Vue from 'vue'

const webinars = require('@/static/json/latest-webinars.json')
const youLearn = require('@/static/json/courses-you-learn.json')

export default {
  layout: 'dashboard',
  fetch({ store }) {
    store.commit('app/SET_DARK_MENU', true)
  },
  data: () => ({
    home: 'home',
    course: webinars[0],
    webinars: _.take(webinars, 3),
    youLearn,
    tab: 0,
    tabs: ['Chat', 'People', 'Poll', 'Resources'],
  }),
  mounted() {
    if (this.$device.isMobile) {
      this.tabs.unshift('Home')
    }
  },
  methods: {
    scrollTo(e, id) {
      if (e) e.preventDefault()
      const el = document.getElementById(id)
      el.scrollIntoView({ behavior: 'smooth' })
    },
    purchaseCourse() {
      this.$store.commit('app/SET_MODAL', 'purchase-modal')
      this.$store.commit('app/SET_VIEW_DATA', {
        type: 'Webinar',
        title: 'How to Build Multiple Sources of Income',
        desc: `Learn how to build and manage multiple sources of 
          income that leads to sustainable wealth`,
        price: 2500,
      })
    },
  },
}
</script>
