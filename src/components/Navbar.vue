<template>
  <nav class="navbar navbar-expand-sm navbar-dark blackBg">
    <!-- <router-link class="navbar-brand d-flex" :to="{ name: 'Home' }"> -->
    <div class="col-12 d-flex justify-content-evenly">
      <div class="text-white">
        <h4> Streak</h4>
      </div>
      <div>
        <h4 class="grayBg text-center">VL</h4>
      </div>
      <div class="text-white">
        <h4>Member Status</h4>
      </div>
    </div>
    <!-- </router-link> -->
    <!-- <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarText"
      aria-controls="navbarText" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarText">

      LOGIN COMPONENT HERE
      <div>
        <button class="btn text-light" @click="toggleTheme">
          <i class="mdi" :class="theme == 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"></i>
        </button>
      </div>
      <Login />
    </div> -->
  </nav>
</template>

<script>
import { onMounted, ref } from 'vue';
import { loadState, saveState } from '../utils/Store.js';
import Login from './Login.vue';
export default {
  setup() {

    const theme = ref(loadState('theme') || 'light')

    onMounted(() => {
      document.documentElement.setAttribute('data-bs-theme', theme.value)
    })

    return {
      theme,
      toggleTheme() {
        theme.value = theme.value == 'light' ? 'dark' : 'light'
        document.documentElement.setAttribute('data-bs-theme', theme.value)
        saveState('theme', theme.value)
      }
    }
  },
  components: { Login }
}
</script>

<style scoped>
a:hover {
  text-decoration: none;
}

.nav-link {
  text-transform: uppercase;
}

.navbar-nav .router-link-exact-active {
  border-bottom: 2px solid var(--bs-success);
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}

@media screen and (min-width: 576px) {
  nav {
    height: 64px;
  }
}

.blackBg {
  background-color: black;
}

.grayBg {
  background-color: rgb(180, 180, 180);
  width: 10dvw;
  height: 6dvh;
}
</style>
