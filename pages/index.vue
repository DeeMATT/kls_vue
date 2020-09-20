<template>
  <div>
    <section class="bg-orange-100">
      <div class="container mx-auto">
        <div class="grid grid-cols-12">
          <div class="col-span-12 md:col-span-6 px-4 lg:px-0">
            <h2 class="title text-4xl md:text-5xl font-bold md:mt-20 pt-10">
              Webinars and courses to up your game 🚀🚀
            </h2>
            <p class="text-md md:text-xl mt-10 mb-8" style="line-height: unset">
              Get relevant and practicable knowledge to kick start your
              business, upskill your career or increase your income.
            </p>
            <search-box />
            <div class="mt-8 mb-6 lg:mb-32">
              <span class="text-xs text-gray-700 block mb-4"
                >Popular searches</span
              >
              <tags-slider :tags="tags" />
            </div>
          </div>
          <img
            src="/home-illust.svg"
            class="lg:absolute lg:top-0 right-0 col-span-12 lg:mt-32"
          />
        </div>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <items-section-group title="Top Categories">
          <div class="grid md:grid-cols-3 lg:grid-cols-4 gap-5">
            <category-item
              v-for="(category, key) in topCategories"
              :key="key"
              :category="category"
            />
          </div>
        </items-section-group>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <div class="grid grid-cols-2 gap-5">
          <div class="col-span-2">
            <h2
              class="text-2xl md:text-3xl lg:text-5xl leading-8 font-semibold text-center mb-5"
            >
              On Klasroom, you can...
            </h2>
          </div>
          <div class="col-span-2 md:col-span-1">
            <icon-card-lg
              icon="/card/course-find-icon.svg"
              title="Take Courses"
              :desc="`Select from a broad range of available courses and start 
                learning right away. These courses are taught by professionals 
                with extensive knowledge and experience.`"
              link-url="/courses"
              link-text="Find a course"
            />
          </div>
          <div class="col-span-2 md:col-span-1">
            <icon-card-lg
              :dark="true"
              bg="bg-blue-400"
              icon="/card/webinar-find-icon.svg"
              title="Attend Webinars"
              :desc="`Select from a broad range of available courses and start 
                learning right away. These courses are taught by professionals 
                with extensive knowledge and experience.`"
              link-url="/webinars"
              link-text="Find a webinar"
            />
          </div>
          <div class="col-span-2 md:col-span-1">
            <icon-card-lg
              :dark="true"
              bg="bg-blue-600"
              icon="/card/course-create-icon.svg"
              title="Create &amp; Sell Courses"
              :desc="`Select from a broad range of available courses and start 
                learning right away. These courses are taught by professionals 
                with extensive knowledge and experience.`"
              link-url="/account/courses/create"
              link-text="Create a course"
            />
          </div>
          <div class="col-span-2 md:col-span-1">
            <icon-card-lg
              :dark="true"
              bg="bg-blue-800"
              icon="/card/webinar-create-icon.svg"
              title="Host &amp; Sell Webinars"
              :desc="`Select from a broad range of available courses and start 
                learning right away. These courses are taught by professionals 
                with extensive knowledge and experience.`"
              link-url="/account/webinars/create"
              link-text="Create a webinar"
            />
          </div>
        </div>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <items-section-group title="Latest Courses" more="/courses/latest">
          <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-5">
            <course-item
              v-for="(course, key) in latestCourses"
              :key="key"
              :course="course"
            />
          </div>
        </items-section-group>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16">
        <why-klasroom />
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <items-section-group title="Trending" more="/trending">
          <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-5">
            <course-item
              v-for="(course, key) in latestCourses"
              :key="key"
              :course="course"
            />
          </div>
        </items-section-group>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16">
        <create-webinar />
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <div class="grid md:grid-cols-2 gap-5">
          <div>
            <items-section-group title="Top Rated Courses" more="/trending">
              <course-item-wide
                v-for="(course, key) in latestCourses"
                :key="key"
                :course="course"
                class="mb-4"
              />
            </items-section-group>
          </div>
          <div>
            <items-section-group title="Top Rated Webinars" more="/trending">
              <webinar-item-wide
                v-for="(webinar, key) in latestCourses"
                :key="key"
                :webinar="webinar"
                class="mb-4"
              />
            </items-section-group>
          </div>
        </div>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16 px-4 lg:px-0">
        <items-section-group title="Latest Webinars" more="/webinars/latest">
          <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-5">
            <webinar-item
              v-for="(webinar, key) in latestCourses"
              :key="key"
              :webinar="webinar"
            />
          </div>
        </items-section-group>
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-16">
        <become-tutor-or-student />
      </div>
    </section>

    <section class="bg-white">
      <div class="container mx-auto my-20">
        <div class="text-center">
          <img src="/logo-gray.svg" class="inline-block mb-4" />
          <div>
            <nuxt-link to="/" class="text-orange-500 underline font-semibold"
              >Click here</nuxt-link
            >
            <span class="text-gray-800"
              >to join our community on Telegram
              <img src="/icon/paper-plane.svg" class="inline-block ml-2 mb-2"
            /></span>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  layout: 'default',
  fetch({ store }) {
    store.commit('app/SET_DARK_MENU', true)
  },
  data: () => ({
    tags: [
      'Bitcoin',
      'Agriculture',
      'Fashion design',
      'Development',
      'Business',
    ],
    topCategories: [
      {
        name: 'Busines and Finance',
        desc: 'Starting your business or seeking funding? Let’s get you sorted',
      },
      {
        name: 'Software Development',
        desc: 'Programming concepts for beginners and advanced learners',
      },
      {
        name: 'Writing',
        desc: 'Say it like you mean it, learn from the best writers',
      },
      {
        name: 'Design',
        desc: 'Hone your visual process and learn design fundamentals.',
      },
    ],
    latestCourses: [
      {
        name: 'Graphic Design for Beginners',
        author: 'Sandra Eze',
        desc: 'Starting your business or seeking funding? Let’s get you sorted',
        photo: '',
      },
      {
        name: 'Graphic Design for Beginners',
        author: 'Sandra Eze',
        desc: 'Starting your business or seeking funding? Let’s get you sorted',
        photo: '',
      },
      {
        name: 'User Interface Design Made Easy',
        author: 'Chimdi BAM',
        desc: 'Programming concepts for beginners and advanced learners',
        photo: '',
      },
      {
        name: 'All About Braids',
        author: 'Sandra Eze',
        desc: 'Starting your business or seeking funding? Let’s get you sorted',
        photo: '',
      },
    ],
  }),
}
</script>

<style scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.title {
  line-height: 120%;
}
</style>
