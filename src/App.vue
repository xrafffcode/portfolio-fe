<script setup>
import { RouterLink, RouterView } from 'vue-router'
import NavbarComponent from './components/Navbar/NavbarComponent.vue';
</script>

<template>
  <NavbarComponent v-if="shouldShowNavbar" />
  <RouterView />
</template>


<script>
export default {
  computed: {
    shouldShowNavbar() {
      return this.$route.path !== '/';
    }
  }
}
</script>