<template>
  <!--
    Tailwind UI components require Tailwind CSS v1.8 and the @tailwindcss/ui plugin.
    Read the documentation to get started: https://tailwindui.com/documentation
  -->
  <div v-if="show" class="fixed z-10 inset-0 overflow-y-auto">
    <div
      class="flex items-start justify-center min-h-screen pt-4 px-4 pb-4 lg:pb-20 text-center sm:block sm:p-0"
    >
      <!--
        Background overlay, show/hide based on modal state.

        Entering: "ease-out duration-300"
          From: "opacity-0"
          To: "opacity-100"
        Leaving: "ease-in duration-200"
          From: "opacity-100"
          To: "opacity-0"
      -->
      <div class="fixed inset-0 transition-opacity">
        <div class="absolute inset-0 bg-gray-500 opacity-75"></div>
      </div>

      <!-- This element is to trick the browser into centering the modal contents. -->
      <span class="hidden sm:inline-block sm:align-middle sm:h-screen"></span
      >&#8203;
      <!--
        Modal panel, show/hide based on modal state.

        Entering: "ease-out duration-300"
          From: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
          To: "opacity-100 translate-y-0 sm:scale-100"
        Leaving: "ease-in duration-200"
          From: "opacity-100 translate-y-0 sm:scale-100"
          To: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
      -->
      <div
        class="inline-block align-top bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle w-full sm:max-w-xl"
        role="dialog"
        aria-modal="true"
        aria-labelledby="modal-headline"
      >
        <div class="bg-white relative px-4 pt-5 pb-4 sm:p-8 sm:pb-5">
          <!-- Close button -->
          <div
            class="absolute top-0 right-0 -ml-8 pt-3 pr-3 flex sm:-ml-10 sm:pr-3"
          >
            <button
              aria-label="Close panel"
              class="text-gray-700 hover:text-gray-500 focus:outline-none transition ease-in-out duration-150"
              @click="$store.commit('app/SET_MODAL', false)"
            >
              <!-- Heroicon name: x -->
              <svg
                class="h-6 w-6"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="1"
                  d="M6 18L18 6M6 6l12 12"
                />
              </svg>
            </button>
          </div>
          <div class="block">
            <div class="text-center mt-3 sm:mt-0 sm:ml-0">
              <img
                src="/icon/congrat-icon.svg"
                class="inline-block mt-4 mb-6 sm:mb-8"
              />
              <h2
                id="modal-headline"
                class="text-xl sm:text-3xl leading-none font-bold text-gray-800 mb-6 sm:mb-8"
              >
                Please rate this {{ type }}
              </h2>
              <div class="mb-4">
                <p v-if="type === 'webinar'" class="text-xs text-gray-700">
                  Thank you for attending. Please rate this webinar from 1 to 5
                  stars based on your experience.
                </p>
                <p v-if="type === 'course'" class="text-xs text-gray-700">
                  Thank you for watching. Please rate this course from 1 to 5
                  stars based on your experience.
                </p>
              </div>
              <div class="rating-stars">
                <rating :grade="3.5" style="zoom: 4" />
                <p class="text-xs text-gray-500">
                  To rate, click a star from the first (lowest) to 5th
                  (highest).
                </p>
              </div>
            </div>
            <hr class="mt-6 mb-6" />
            <div class="mt-3 sm:mt-0 sm:ml-0">
              <!-- Rating form -->
              <form id="rating-form" @submit.prevent="">
                <div class="form-group mb-5">
                  <label for="input-review">
                    Please describe your experience
                  </label>
                  <div>
                    <input
                      id="input-review"
                      class="form-input"
                      placeholder="Enter review here"
                    />
                  </div>
                </div>
                <hr class="mt-6 mb-6" />
                <div class="flex text-center pb-4 sm:pb-4">
                  <button
                    class="btn btn-primary block sm:inline-block mx-auto shadow"
                  >
                    Submit
                  </button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
      <!-- End login card -->
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  props: {
    type: { type: String, required: true },
  },
  computed: {
    ...mapState({
      show: (state) => state.app.modal === 'completed-rating-modal',
    }),
  },
}
</script>
