<template>
  <!--
    Tailwind UI components require Tailwind CSS v1.8 and the @tailwindcss/ui plugin.
    Read the documentation to get started: https://tailwindui.com/documentation
  -->
  <div v-if="showLogin" class="fixed z-10 inset-0 overflow-y-auto">
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
        class="inline-block align-top bg-white rounded-lg text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle w-full sm:max-w-lg"
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
              @click="$store.commit('app/LOGIN_MODAL', false)"
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
          <toggle-switch
            v-model="isLogin"
            active="Sign up"
            inactive="Sign in"
            class="mb-6"
          />
          <div class="block">
            <div class="mt-3 sm:mt-0 sm:ml-0">
              <h2
                id="modal-headline"
                class="text-xl sm:text-4xl leading-none font-bold text-center text-gray-800"
              >
                {{
                  isLogin
                    ? 'Sign into your account'
                    : 'Create a student account'
                }}
              </h2>
              <hr class="mt-8 mb-5" />
              <!-- Login form -->
              <form v-if="isLogin" id="login-form">
                <div class="form-group mb-5">
                  <label for="input-email">Email address</label>
                  <div>
                    <input
                      id="input-email"
                      class="form-input"
                      placeholder="Enter your email here"
                    />
                  </div>
                </div>
                <div class="form-group">
                  <label for="input-password">Password</label>
                  <div>
                    <input
                      id="input-password"
                      class="form-input"
                      placeholder="Enter your password here"
                    />
                  </div>
                </div>
                <div class="flex text-center pt-8 pb-4 sm:pb-4">
                  <span class="flex mx-auto">
                    <button
                      type="button"
                      class="btn btn-primary shadow"
                      @click="gotoStudentDash"
                    >
                      Sign in
                    </button>
                  </span>
                </div>
                <hr class="mt-4 mb-4" />
                <div class="text-center">
                  <a
                    href="#"
                    class="text-sm leading-5 text-gray-700"
                    @click="forgotPassword"
                  >
                    Forgot password?
                  </a>
                </div>
              </form>
              <!-- Sign up form -->
              <form v-else id="signup-form">
                <div class="form-group mb-5">
                  <label for="input-name">Name</label>
                  <div>
                    <input
                      id="input-name"
                      class="form-input"
                      placeholder="Enter your name here"
                    />
                  </div>
                </div>
                <div class="form-group mb-5">
                  <label for="input-email">Email address</label>
                  <div>
                    <input
                      id="input-email"
                      class="form-input"
                      placeholder="Enter your email here"
                    />
                  </div>
                </div>
                <div class="form-group">
                  <label for="input-password">Password</label>
                  <div>
                    <input
                      id="input-password"
                      class="form-input"
                      placeholder="Enter your password here"
                    />
                  </div>
                </div>
                <div class="flex text-center pt-8 pb-4 sm:pb-4">
                  <span class="flex mx-auto">
                    <button
                      type="button"
                      class="btn btn-primary shadow"
                      @click="showSuccess"
                    >
                      Sign up
                    </button>
                  </span>
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
  data: () => ({
    isLogin: true,
  }),
  computed: {
    ...mapState({
      showLogin: (state) => state.app.loginModal,
    }),
  },
  watch: {
    showLogin: {
      handler(value) {
        // console.log('showLogin', value)
        if (value) this.isLogin = value !== 'register'
      },
      immediate: true,
    },
  },
  methods: {
    forgotPassword(e) {
      if (e) e.preventDefault()
      this.$store.commit('app/FORGOT_PASSWORD_MODAL', true)
      this.$store.commit('app/LOGIN_MODAL', false)
    },
    showSuccess(e) {
      if (e) e.preventDefault()
      this.$store.commit('app/NOTICE_MODAL', {
        title: 'All done!',
        text: `You have successfully signed up to klasroom.com. 
          Please check your email and click the link in it to 
          complete your registration.`,
      })
      this.$store.commit('app/LOGIN_MODAL', false)
    },
    gotoStudentDash() {
      this.$store.commit('app/LOGIN_MODAL', false)
      this.$router.push('/student/dashboard')
    },
  },
}
</script>
