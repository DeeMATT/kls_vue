<template>
  <div class="relative bg-orange-200 rounded-lg p-10 py-20 mt-12">
    <img
      src="/card/yellow-squares.png"
      class="absolute -mt-32 -mr-40 right-0"
    />
    <div class="grid grid-cols-2 gap-6">
      <div class="grid grid-cols-12 gap-4">
        <div class="col-span-5 pb-5">
          <h4 class="text-4xl font-bold" style="line-height: 120%">
            Become a tutor
          </h4>
        </div>
        <div class="col-span-5 pb-5">
          <p class="text-md pb-2 mt-2">
            Have you been there, done that? Turn your knowledge to cash
          </p>
        </div>
        <div class="col-span-12">
          <nuxt-link to="/" class="btn btn-primary"
            >Create tutor account now</nuxt-link
          >
        </div>
      </div>
      <div class="grid grid-cols-12 gap-4">
        <div class="col-span-5">
          <h4 class="text-4xl font-bold pb-5" style="line-height: 120%">
            Become a student
          </h4>
        </div>
        <div class="col-span-6 pb-5">
          <p class="text-md pb-2 mt-2">
            Learn from seasoned experts and turn your insights to cash
          </p>
        </div>
        <div class="col-span-12">
          <nuxt-link to="/" class="btn btn-primary"
            >Create student account now</nuxt-link
          >
        </div>
      </div>
    </div>
    <img src="/card/red-bubbles.png" class="absolute -mt-32 -ml-64 left-0" />
  </div>
</template>

<style scoped>
li {
  display: block;
  padding: 5px 0 5px 25px;
  position: relative;
  line-height: 28px;
}
li::before {
  content: '';
  display: inline-block;
  position: absolute;
  border-radius: 6px;
  width: 12px;
  height: 12px;
  left: 0;
  top: 12.5px;
  background: #f99e42;
}
</style>
