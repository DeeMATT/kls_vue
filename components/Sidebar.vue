<template>
  <div class="sidebar" :class="menu ? 'open' : 'closed'">
    <span class="overlay" @click="toggleNav"></span>
    <div class="mt-5 relative">
      <button
        variant="light"
        class="menu-close my-auto text-left outline-none focus:outline-none lg:hidden"
        @click="toggleNav"
      >
        <img src="~/static/close.svg" />
      </button>
      <div class="px-4 lg:col-span-1 text-right lg:text-center">
        <router-link :to="{ name: 'student-dashboard' }">
          <img
            src="~/static/logo.svg"
            alt="Casava.co"
            class="ml-auto lg:mx-auto w-7/12 lg:w-auto"
          />
        </router-link>
      </div>
    </div>
    <div class="menu-scroll h-screen pb-40">
      <nav class="h-full">
        <ul class="relative h-full">
          <li class="nav-item">
            <router-link
              :to="{ name: 'student-dashboard' }"
              class="nav-link nav-home"
              active-class="active"
              exact
            >
              Dashboard
            </router-link>
          </li>
          <li class="nav-item">
            <router-link
              :to="{ name: 'student-courses' }"
              class="nav-link nav-courses"
              active-class="active"
              exact
            >
              Courses
            </router-link>
          </li>
          <li class="nav-item">
            <router-link
              :to="{ name: 'student-webinars' }"
              class="nav-link nav-webinars"
              active-class="active"
              exact
            >
              Webinars
            </router-link>
          </li>
          <li class="nav-item">
            <router-link
              :to="{ name: 'student-chat' }"
              class="nav-link nav-chat"
              active-class="active"
              exact
            >
              Chat
            </router-link>
          </li>
          <li class="nav-item">
            <router-link
              :to="{ name: 'dashboard-help' }"
              class="nav-link nav-help"
              active-class="active"
              exact
            >
              Help
            </router-link>
          </li>
          <li class="nav-item pt-md-4 mt-5 lg:absolute bottom-0 w-full">
            <hr class="sidebar-divider mx-8 mb-4" />
            <router-link
              :to="{ name: 'telegram' }"
              class="nav-link nav-telegram"
              active-class="active"
              exact
            >
              <span class="text-xs">Join Telegram Community</span>
            </router-link>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  data: () => ({
    appName: process.env.appName,
  }),

  computed: mapGetters({
    menu: 'app/menu',
    user: 'auth/user',
  }),

  methods: {
    toggleNav(e) {
      if (e) e.preventDefault()

      this.$store.commit('app/TOGGLE_MENU', !this.menu)
    },
    async logout() {
      // Log out the user.
      await this.$store.dispatch('auth/logout')

      // Redirect to login.
      this.$router.push({ name: 'login' })
    },
  },
}
</script>

<style scoped>
.sidebar {
  display: flex;
  flex-direction: column;
  width: 260px;
  min-width: 260px;
  z-index: 2001;
  min-height: 100%;
  background: #fff;
  box-shadow: 0 0 24px rgba(0, 0, 0, 0.04);
}

.sidebar .overlay {
  display: none;
  position: absolute;
  left: 265px;
  top: 0;
  width: 1000px;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

nav {
  margin-top: 50px;
  margin-bottom: 35px;
}

ul {
  /* padding: 0; */
}

li {
  list-style: none;
  margin: 0;
}

a.round {
  border-radius: 25px;
}

ul.btn-gray-share > li {
  padding: 10px;
  margin-right: 10px;
}

.nav-link {
  text-decoration: none;
  display: block;
  padding: 10px 15px 10px 55px;
  margin-top: 5px;
  background-repeat: no-repeat;
  background-position: left 25px top 50%;
  line-height: 22px;
  @apply text-sm text-gray-700;
}
.nav-link:hover {
  text-decoration: none;
  color: initial;
}
.nav-link.active {
  border-right: 5px solid;
  line-height: 21px;
  @apply font-bold border-orange-500 text-gray-900;
}
.nav-link.nav-home {
  background-image: url('/icon/dashboard/dashboard.svg');
}
.nav-link.nav-courses {
  background-image: url('/icon/dashboard/courses.svg');
}
.nav-link.nav-webinars {
  background-image: url('/icon/dashboard/webinars.svg');
}
.nav-link.nav-chat {
  background-image: url('/icon/dashboard/chat.svg');
}
.nav-link.nav-help {
  background-image: url('/icon/dashboard/help.svg');
}
.nav-link.nav-telegram {
  background-image: url('/icon/dashboard/telegram.svg');
}

.menu-close {
  position: absolute;
  top: 0;
  left: 16px;
  background: transparent !important;
  border: 0 !important;
}

@media (max-width: 768px) {
  .menu-scroll {
    height: 100%;
    position: relative;
    display: grid;
    overflow-y: scroll;
  }
}

@media (max-width: 1124px) {
  .App-logo {
    width: 98px;
  }
  nav {
    margin-top: 0;
  }
  .mb-logo-top {
    padding: 8px 0;
    border-bottom: 1px solid rgba(0, 0, 0, 0.05);
  }
  .sidebar.closed {
    position: absolute;
    left: -265px;
  }
  .sidebar.open {
    position: fixed;
    left: 0;
    background-color: #fff;
    height: 100%;
    min-height: 100vh;
    transition: 0.28s;
  }
  .sidebar.open .overlay {
    display: block;
    transition: 0.32s;
  }
}
</style>
