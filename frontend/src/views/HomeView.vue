<script setup></script>

<template>
  <div class="home">
    <section class="hero-section">
      <!-- Left Content -->
      <div class="hero-content glass-box">
        <div class="badge">Open to Collaborations 🚀</div>

        <h1 class="title-massive">
          Hi, I me <br />
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
          <button class="btn-primary">Explore Work</button>
          <a href="#contact" class="btn-outline">Hire Me</a>
        </div>
      </div>

      <!-- Right Content (Image) -->
      <div class="hero-image-container glass-box">
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
  max-width: 1200px; /* Reduced from 1400px to avoid looking too stretched on 100% width */
  margin: 0 auto;
  min-height: calc(100vh - 80px); /* Fill screen minus navbar space */
  display: flex;
  align-items: center;
  padding: 40px 20px;
}

.hero-section {
  width: 100%;
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 30px; /* Reduced gap */
  align-items: stretch; /* FORCES EQUAL HEIGHT */
}

/* Left Content Styles */
.hero-content {
  padding: 60px 50px; /* Reduced padding from 80px */
  display: flex;
  flex-direction: column;
  justify-content: center;
  /* Enter animation */
  animation: slideInLeft 1s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards;
}

.badge {
  align-self: flex-start;
  background: white;
  color: var(--accent-1);
  padding: 6px 16px; /* Scaled down */
  border-radius: 50px;
  font-weight: 700;
  font-size: 0.8rem; /* Scaled down */
  margin-bottom: 20px;
  box-shadow: 0 4px 15px rgba(37, 99, 235, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.8);
}

.title-massive {
  margin-bottom: 15px;
  color: var(--text-main);
  /* font-size is handled by main.css utility */
}

.hero-role {
  font-size: 1.4rem; /* Scaled down from 1.8rem */
  font-weight: 500;
  color: var(--text-muted);
  margin-bottom: 20px;
  letter-spacing: -0.5px;
}

.hero-role span {
  color: var(--text-main);
  font-weight: 700;
  position: relative;
}

.hero-desc {
  font-size: 1.05rem; /* Scaled down from 1.2rem */
  color: var(--text-muted);
  max-width: 480px; /* Reduced max-width */
  margin-bottom: 35px;
  line-height: 1.7;
}

.action-buttons {
  display: flex;
  gap: 15px;
}

.btn-outline {
  padding: 14px 30px; /* Scaled down slightly */
  border-radius: 12px;
  font-family: var(--font-main);
  font-weight: 600;
  font-size: 1rem;
  color: var(--text-main);
  background: white;
  border: 1px solid var(--border-glass);
  transition: var(--transition-smooth);
}

.btn-outline:hover {
  background: var(--text-main);
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
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

/* Responsive */
@media (max-width: 1024px) {
  .hero-section {
    grid-template-columns: 1fr;
    gap: 30px;
    margin-top: 40px;
  }
}
</style>
