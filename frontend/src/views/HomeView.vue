<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
  <div class="home">
    <section class="hero-section">
      <!-- Left Content -->
      <div class="hero-content glass-box animate-left">
        <div class="badge">Open to Collaborations 🚀</div>

        <h1 class="title-massive">
          Hi, I am <br />
          <span class="text-gradient">Fathi Rizki Ammar.</span>
        </h1>

        <h2 class="hero-role">
          Software Engineer,
          <span>Web & AI Specialist</span>
        </h2>

        <p class="hero-desc">
          Building the next generation of digital experiences through robust
          backend architecture and high-performance frontends. Committed to
          quality and elegant design.
        </p>

        <div class="action-buttons">
          <RouterLink to="/dashboard" class="btn-primary">Explore Work</RouterLink>
          <RouterLink to="/contact" class="btn-outline">Contact Me</RouterLink>
        </div>
      </div>

      <!-- Right Content (Image) -->
      <div class="hero-image-container glass-box animate-right">
        <img
          src="../assets/hero.png"
          alt="Developer Illustration"
          class="hero-image"
        />
      </div>
    </section>
  </div>
</template>

<style scoped>
.home {
  max-width: 1350px;
  margin: 0 auto;
  min-height: calc(100vh - 120px);
  display: flex;
  align-items: center;
  padding: 40px 20px;
}

/* Hero Grid Layout */
.hero-section {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 60px;
  width: 100%;
  align-items: center;
}

.hero-content {
  padding: 60px;
  /* Glass effect already defined in main.css */
}

/* Animations */
.animate-left { animation: slideInLeft 1s ease-out forwards; }
.animate-right { animation: slideInRight 1.2s ease-out forwards; }

.badge {
  display: inline-block;
  background: rgba(37, 99, 235, 0.1);
  color: var(--accent-1);
  padding: 8px 16px;
  border-radius: 50px;
  font-size: 0.85rem;
  font-weight: 600;
  margin-bottom: 20px;
}

.title-massive {
  margin-bottom: 15px;
  color: var(--text-main);
  /* font-size is handled by main.css utility */
}

.btn-primary:hover, .btn-outline:hover {
  background: var(--text-main);
  color: white;
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.1);
  border-color: transparent;
}

/* Right Content (Image) Styles */
.hero-image-container {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px; /* Reduced from 40px */
  position: relative;
  /* Enter animation */
  animation: slideInRight 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
}

.hero-image {
  width: 100%;
  max-width: 420px; /* Scaled down from 550px for balance */
  height: auto;
  border-radius: 20px;
  filter: drop-shadow(0 20px 40px rgba(0, 0, 0, 0.05));
  /* Floating animation */
  animation: float 6s ease-in-out infinite;
}

/* Animations Keyframes */
@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-40px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(40px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes float {
  0% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-10px);
  }
  100% {
    transform: translateY(0px);
  }
}

.hero-desc {
  font-size: 1.1rem;
  color: var(--text-muted);
  max-width: 550px;
  margin-bottom: 40px;
  line-height: 1.8;
}

.action-buttons {
  display: flex;
  gap: 20px;
  align-items: center;
}

.btn-primary, .btn-outline {
  padding: 16px 36px;
  border-radius: 14px;
  font-weight: 700;
  font-size: 1rem;
  text-align: center;
  transition: var(--transition-smooth);
  display: inline-block;
  min-width: 180px;
}

.btn-primary {
  background: var(--text-main);
  color: white;
  border: none;
  box-shadow: 0 10px 20px rgba(30, 41, 59, 0.15);
}

.btn-outline {
  background: transparent;
  color: var(--text-main);
  border: 2px solid var(--text-main);
}

.btn-primary:hover {
  background: var(--accent-1);
  color: white;
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 15px 30px rgba(37, 99, 235, 0.25);
}

.btn-outline:hover {
  background: var(--text-main);
  color: white;
  transform: translateY(-5px) scale(1.05);
  box-shadow: 0 15px 30px rgba(30, 41, 59, 0.15);
}

/* Tablet & Mobile Responsiveness */
@media (max-width: 1024px) {
  .hero-section {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 40px;
    margin-top: 50px;
  }

  .hero-content {
    padding: 30px;
    align-items: center;
  }

  .hero-desc { margin: 0 auto 40px; }
  .action-buttons { justify-content: center; }
}

@media (max-width: 640px) {
  .title-massive { font-size: 2.2rem; }
  .action-buttons {
    flex-direction: column;
    width: 100%;
    gap: 15px;
  }
  .btn-primary, .btn-outline {
    width: 100%;
    min-width: unset;
  }
}
</style>
