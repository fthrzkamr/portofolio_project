<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <header class="navbar glass-box">
    <div class="nav-container">
      <div class="logo">
        <RouterLink to="/">
          <span class="text-gradient">FA.</span>Dev
        </RouterLink>
      </div>

      <nav class="nav-links">
        <RouterLink to="/" class="nav-link">Home</RouterLink>
        <RouterLink to="#about" class="nav-link">About</RouterLink>
        <RouterLink to="#projects" class="nav-link">Projects</RouterLink>
        <RouterLink to="/login" class="nav-btn">Login</RouterLink>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.navbar {
  position: fixed;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  width: 90%;
  max-width: 1200px;
  border-radius: 60px; /* Pill */
  z-index: 1000;
  padding: 10px 30px;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo a {
  font-weight: 800;
  font-size: 1.5rem; /* Down from 1.8rem */
  letter-spacing: -1px;
  color: var(--text-main);
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 30px;
}

.nav-link {
  font-weight: 600;
  font-size: 0.95rem; /* Down from 1rem */
  color: var(--text-muted);
  transition: var(--transition-smooth);
  position: relative;
}

.nav-link:hover,
.router-link-active {
  color: var(--text-main);
}

.nav-link::after {
  content: "";
  position: absolute;
  width: 0%;
  height: 3px;
  bottom: -6px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--gradient-main);
  transition: var(--transition-smooth);
  border-radius: 3px;
}

.nav-link:hover::after,
.router-link-active::after {
  width: 100%;
}

.nav-btn {
  font-weight: 700;
  font-size: 0.9rem;
  color: var(--text-main);
  border: 1px solid var(--border-glass);
  background: white;
  padding: 8px 20px;
  border-radius: 50px;
  transition: var(--transition-smooth);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.03);
}

.nav-btn:hover {
  background: var(--text-main);
  border-color: var(--text-main);
  color: white;
}
</style>
