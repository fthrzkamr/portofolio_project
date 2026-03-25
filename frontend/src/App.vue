<script setup>
import { RouterView } from "vue-router";
import Navbar from "./components/Navbar.vue";
</script>

<template>
  <div class="app-layout">
    <Navbar />
    <!-- RouterView is where the active page (like HomeView) will be rendered! -->
    <main class="page-content">
      <RouterView />
    </main>
  </div>
</template>

<style scoped>
.app-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.page-content {
  flex: 1;
  padding-top: 80px; /* Space for fixed navbar */
}
</style>
