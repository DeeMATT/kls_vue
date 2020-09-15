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
              Get relevant and practicable knowledge to kick start your business,
              upskill your career or increase your income.
            </p>
          </div>
          <img src="/home-illust.svg" class="absolute top-40 right-0" />
        </div>
      </div>
    </section>
    <section class="bg-white">
      <div class="container mx-auto my-10">
        <h5 class="prose-xl font-semibold text-gray-600 mb-8">Top Categories</h5>
        <div class="grid grid-cols-4 gap-5">
          <a
            v-for="category in topCategories"
            :key="category.name"
            class="bg-white rounded-lg border border-gray-300 hover:shadow-lg p-6 relative"
          >
            <span class="inline-block bg-gray-100 w-20 h-20 rounded-lg"></span>
            <p class="prose-2xl text-orange-500 font-semibold my-3">{{ category.name }}</p>
            <p>{{ category.desc }}</p>
            <div class="text-center absolute bottom-0 mb-5">
              <nuxt-link to="/" class="text-black"> View more </nuxt-link>
            </div>
          </a>
        </div>

        <div class="bg-gray-200 rounded-lg p-10 py-16 mt-12">
          <div class="grid grid-cols-4">
            <div>Why Klasroom?</div>
            <div>
              Learn at your own pace and from anywhere
            </div>
            <div>
              Flexible payment options that allows for pay as you go.
            </div>
            <div>
              Learn from Africa’s most successful Entrepreneurs
            </div>
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
