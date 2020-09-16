<template>
  <div>
    <section class="bg-orange-100">
      <div class="container mx-auto min-h-screen">
        <div class="grid grid-cols-12">
          <div class="col-span-7">
            <h2 class="title font-bold mt-20">
              Relevant knowledge to start earning immediately
            </h2>
            <p class="prose-xl mt-10" style="line-height: unset">
              Get relevant and practicable knowledge to kick start your
              business, upskill your career or increase your income.
            </p>
          </div>
          <img src="/home-illust.svg" class="absolute top-40 right-0" />
        </div>
      </div>
    </section>
    <section class="bg-white">
      <div class="container mx-auto my-16">
        <ItemsSectionGroup title="Top Categories">
          <div class="grid grid-cols-4 gap-5">
            <category-item
              v-for="(category, key) in topCategories"
              :key="key"
              :category="category"
            />
          </div>
        </ItemsSectionGroup>
      </div>
    </section>
    <section class="bg-white">
      <div class="container mx-auto my-16">
        <ItemsSectionGroup title="Latest Courses" more="/courses/latest">
          <div class="grid grid-cols-4 gap-5">
            <course-item
              v-for="(course, key) in latestCourses"
              :key="key"
              :course="course"
            />
          </div>
        </ItemsSectionGroup>
      </div>
    </section>
    <!-- <section class="bg-white">
      <div class="container mx-auto my-16">
        <div class="bg-gray-200 rounded-lg p-10 py-16 mt-12">
          <div class="grid grid-cols-4">
            <div>Why Klasroom?</div>
            <div>Learn at your own pace and from anywhere</div>
            <div>Flexible payment options that allows for pay as you go.</div>
            <div>Learn from Africa’s most successful Entrepreneurs</div>
          </div>
        </div>
      </div>
    </section> -->
    <section class="bg-white">
      <div class="container mx-auto my-16">
        <ItemsSectionGroup title="Latest Webinars" more="/webinars/latest">
          <div class="grid grid-cols-4 gap-5">
            <webinar-item
              v-for="(webinar, key) in latestCourses"
              :key="key"
              :webinar="webinar"
            />
          </div>
        </ItemsSectionGroup>
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
  data: () => ({
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
  font-size: 48px;
  line-height: 120%;
}
</style>
