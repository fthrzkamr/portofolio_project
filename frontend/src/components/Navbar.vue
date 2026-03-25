<script setup>
import { RouterLink } from "vue-router";
import { useRoute } from 'vue-router';

const route = useRoute();
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
        <!-- Navigation Links (Hidden on Home Page) -->
        <template v-if="route.path !== '/'">
          <a href="#profile" class="nav-link">Home</a>
          <a href="#about" class="nav-link">About</a>
          <a href="#projects" class="nav-link">Projects</a>
          <a href="#contact" class="nav-link">Contact</a>
        </template>
        <RouterLink to="/login" class="nav-btn-dark">Login</RouterLink>
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
  font-size: 0.95rem;
  color: var(--text-muted);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  padding: 8px 4px;
  position: relative;
  display: inline-block;
}

.router-link-active {
  color: var(--text-main);
}

.nav-link:hover {
  color: var(--text-main);
  transform: translateY(-6px) scale(1.1); /* Visible ONLY on hover */
  z-index: 10;
}

/* Elegant Center Underline */
.nav-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  bottom: -4px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--text-main);
  transition: width 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.nav-link:hover::after, .router-link-active::after {
  width: 100%;
}

.nav-link:active {
  transform: scale(0.9);
}

.nav-btn-dark {
  font-weight: 700;
  font-size: 0.9rem;
  color: white;
  background: var(--text-main);
  padding: 8px 24px;
  border-radius: 50px;
  transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.nav-btn-dark:hover {
  transform: translateY(-3px) scale(1.05);
  box-shadow: 0 8px 20px rgba(30, 41, 59, 0.15);
}

/* Responsive Navbar */
@media (max-width: 768px) {
  .navbar {
    top: 10px;
    width: 95%;
    padding: 10px 20px;
    border-radius: 40px;
  }

  .nav-container {
    flex-direction: column; /* Stack logo and links for more space */
    gap: 12px;
  }

  .logo a {
    font-size: 1.3rem;
  }

  .nav-links {
    gap: 20px;
    justify-content: center;
    width: 100%;
  }

  .nav-link {
    font-size: 0.85rem;
  }

  .nav-btn {
    display: none; /* Hide old button in mobile nav for cleaner look */
  }
}

@media (max-width: 480px) {
  .nav-links {
    gap: 15px;
  }
  
  .nav-link {
    font-size: 0.8rem;
  }
}
</style>
