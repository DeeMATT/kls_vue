<template>
  <div class="container mx-auto">
    <nav class="flex items-center justify-between flex-wrap py-4 md:py-6">
      <h5
        class="flex items-center flex-shrink-0 mr-6 ml-4 lg:ml-0 font-extrabold text-gray-700"
      >
        {{ title }}
      </h5>
      <div class="block lg:hidden mr-4 lg:mr-0">
        <button
          class="flex items-center px-3 py-2 border rounded text-gray-700 border-gray-900"
          @click="toggleMenu"
        >
          <svg
            class="fill-current h-3 w-3"
            viewBox="0 0 20 20"
            xmlns="http://www.w3.org/2000/svg"
          >
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div :class="{ hidden: !open }" class="menu-group">
        <div class="mx-auto" @click="toggleMenu">
          <NavSearchBox />
        </div>
        <div
          class="mt-8 md:mt-0 mb-6 md:mb-0 lg:border-l border-gray-400 lg:pl-6"
        >
          <div class="notification mr-3">
            <span>{{ 0 }}</span>
          </div>
          <a
            href="#"
            class="user-menu lg:mt-0 block md:inline-block"
            @click="toggleRegister"
          >
            <span
              class="user-avatar mr-1"
              :style="{ backgroundImage: 'url(/avatar.jpg)' }"
            ></span>
            <div class="inline-block text-left text-xs mr-2 pt-1">
              <span class="block text-gray-800 font-bold leading-tight">
                Oluwadamilare Adedeji
              </span>
              <span class="block text-gray-600">damilare@gmail.com</span>
            </div>
          </a>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data: () => ({
    open: false,
  }),
  computed: {
    ...mapState({
      darkMenu: (state) => state.app.darkMenu,
      title: (state) => state.app.pageTitle,
    }),
  },
  methods: {
    toggleMenu() {
      this.open = !this.open
    },
    toggleLogin(e) {
      if (e) e.preventDefault()
      this.open = false
      this.$store.commit('app/LOGIN_MODAL', 'login')
    },
    toggleRegister(e) {
      if (e) e.preventDefault()
      this.open = false
      this.$store.commit('app/LOGIN_MODAL', 'register')
    },
  },
}
</script>

<style scoped>
.menu-group {
  @apply transition duration-500;
  @apply w-full flex-grow bg-white mt-5 shadow-lg px-4;
}
.menu-item {
  @apply text-sm text-black mr-8;
}
.menu-item:hover {
  @apply text-orange-500;
}
.menu-item.has-child {
  background-image: url('/actions/arrow-down.svg');
  background-repeat: no-repeat;
  background-position: right 0 top 8px;
  padding-right: 24px;
}
.notification {
  position: relative;
  display: inline-block;
  background-color: rgba(249, 158, 66, 0.2);
  border-radius: 12px;
  background-image: url('/icon/notice-bell.svg');
  background-repeat: no-repeat;
  background-position: 50%;
  width: 48px;
  height: 48px;
  vertical-align: middle;
}
.notification > span {
  display: inline-block;
  padding: 0 3px;
  position: absolute;
  background-color: rgb(255, 51, 95);
  border-radius: 7.5px;
  color: #fff;
  font-size: 10px;
  font-weight: 600;
  cursor: pointer;
  top: 8px;
  right: 8px;
}
.user-menu {
  background-image: url('/icon/dash-user-drop.svg');
  background-repeat: no-repeat;
  background-position: top 50% right 17px;
  padding: 3px;
  @apply border border-gray-400 rounded-xl pr-12;
  @apply align-bottom;
}
.user-avatar {
  border-radius: 7.5px;
  background-color: #e9e9e9;
  display: inline-block;
  width: 40px;
  height: 40px;
  vertical-align: bottom;
  background-repeat: no-repeat;
  background-size: cover;
}
@media (min-width: 768px) {
  .menu-group {
    @apply flex items-center w-auto shadow-none;
    @apply bg-transparent px-0 mt-0;
  }
}
</style>
