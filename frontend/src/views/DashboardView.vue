<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import { RouterLink } from 'vue-router';

const showScrollTop = ref(false);

const handleScroll = () => {
  showScrollTop.value = window.scrollY > 300;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <div class="dashboard-page animate-in">
    <!-- Navigation Controls -->
    <div class="floating-controls">
      <!-- Back to Splash (3D House Style) -->
      <RouterLink to="/" class="control-btn exit-btn floating-3d" title="Back to Welcome">
        <span class="icon">🏠</span>
      </RouterLink>

      <!-- Scroll to Top (Rocket Style - Visible only on Scroll) -->
      <transition name="fade">
        <a href="#profile" v-if="showScrollTop" class="control-btn up-btn" title="Back to Top">
          <span class="icon">🚀</span>
        </a>
      </transition>
    </div>

    <div class="dashboard-container">
      
      <!-- ======== 1. Personal Profile (Photo + Story) ======== -->
      <section id="profile" class="profile-hero glass-box">
        <div class="story-content">
          <span class="section-badge">Personal Profile</span>
          <h2 class="title-sub">Software Engineering is My Passion</h2>
          <p class="section-text-large">
            Saya mengawali perjalanan saya dari rasa penasaran tentang bagaimana sebuah website bekerja. 
            Hobi inilah yang kemudian menuntun saya menjadi seorang **Software Engineer** yang berfokus pada 
            solusi teknis yang elegan dan efisien. Saya selalu percaya bahwa kode yang baik adalah kode 
            yang bisa memudahkan kehidupan orang lain.
          </p>
        </div>
        <div class="photo-container">
          <div class="photo-frame">
            <img src="../assets/hero.png" alt="My Photo" class="profile-photo" />
          </div>
        </div>
      </section>

      <!-- ======== 2. About Me (Riwayat Hidup & Pendidikan) ======== -->
      <section id="about" class="about-journey-section">
        <div class="glass-box full-card">
          <div class="section-header centered">
            <span class="section-badge">About My Journey</span>
            <h2 class="title-sub">Biography & Education</h2>
          </div>
          
          <div class="bio-grid">
            <div class="bio-text">
              <h4>Siapa Saya?</h4>
              <p>
                Saya adalah seorang profesional yang berdedikasi tinggi dalam dunia teknologi. 
                Memiliki keahlian khusus di bidang Backend Architecture menggunakan Django dan 
                Frontend modern menggunakan Vue.js. Sejak masih di bangku sekolah, saya aktif 
                mengikuti berbagai kompetisi teknologi dan pelatihan sertifikasi nasional.
              </p>
            </div>
            
            <div class="education-timeline">
              <h4>Riwayat Pendidikan</h4>
              <div class="timeline-v2">
                <div class="t-item">
                  <span class="t-year">2020 - 2024</span>
                  <h5>S1 Teknik Informatika</h5>
                  <p>Universitas Teknologi Nasional - Lulus dengan Cum Laude.</p>
                </div>
                <div class="t-item">
                  <span class="t-year">2017 - 2020</span>
                  <h5>SMA Jurusan MIPA</h5>
                  <p>SMA Negeri Unggulan No. 1 - Fokus pada Kompetisi Matematika.</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- ======== 3. Projects Showcase (Sudah Dibuat) ======== -->
      <section id="projects" class="projects-container">
        <div class="section-header centered">
          <span class="section-badge">Recent Projects</span>
          <h2 class="title-sub">Featured Creations</h2>
        </div>

        <div class="project-grid">
          <div class="project-item glass-box">
            <div class="project-thumb">
              <img src="https://images.unsplash.com/photo-1551288049-bbbda536639a?q=80&w=400" alt="Work 1" />
            </div>
            <div class="project-info">
              <h4>HRIS Dashboard System</h4>
              <p>Solusi Manajemen Karyawan Berbasis Cloud.</p>
            </div>
          </div>

          <div class="project-item glass-box">
            <div class="project-thumb">
              <img src="https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=400" alt="Work 2" />
            </div>
            <div class="project-info">
              <h4>AI Image Recognition</h4>
              <p>Identifikasi Objek Secara Real-time Menggunakan Python.</p>
            </div>
          </div>

          <div class="project-item glass-box">
            <div class="project-thumb">
              <img src="https://images.unsplash.com/photo-1460925895917-afdab827c52f?q=80&w=400" alt="Work 3" />
            </div>
            <div class="project-info">
              <h4>Personal Portfolio Engine</h4>
              <p>Website Portofolio Dinamis dengan CMS Django.</p>
            </div>
          </div>
        </div>
      </section>

      <!-- ======== 4. Contact Section ======== -->
      <section id="contact" class="contact-footer">
        <div class="glass-box contact-card">
          <h2 class="title-sub">Let's Talk!</h2>
          <p>Terbuka untuk peluang kerja, proyek lepas, maupun kolaborasi startup.</p>
          <div class="contact-links">
            <a href="mailto:hello@example.com" class="c-link">📧 Email Me</a>
            <a href="#" class="c-link">🔗 LinkedIn</a>
            <a href="#" class="c-link">📱 WhatsApp</a>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
.dashboard-page { max-width: 1400px; margin: 0 auto; padding: 40px 20px 80px 20px; position: relative; }
.animate-in { animation: fadeIn 0.8s ease-out; }

/* Dashboard Control Center Styles */
.exit-btn {
  position: fixed;
  top: 100px;
  right: 40px;
  z-index: 1000;
  animation: floatIcon 3s ease-in-out infinite;
}

.up-btn {
  position: fixed;
  bottom: 40px;
  right: 40px;
  z-index: 1000;
}

.control-btn {
  width: 60px;
  height: 60px;
  background: white;
  border: 1px solid var(--border-glass);
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.8rem;
  box-shadow: 0 8px 25px rgba(0,0,0,0.1);
  cursor: pointer;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.control-btn:hover {
  background: var(--text-main);
  color: white;
  transform: scale(1.15); /* Keep it straight */
  box-shadow: 0 15px 35px rgba(0,0,0,0.15);
}

.up-btn:hover {
  transform: translateY(-10px) scale(1.1); /* Rocket luncher straight up */
}

@keyframes floatIcon {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}

/* Fade Transition for Scroll-to-Top Button */
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.4s, transform 0.4s;
}
.fade-enter-from, .fade-leave-to {
  opacity: 0;
  transform: scale(0.5) translateY(20px);
}

.dashboard-container { display: flex; flex-direction: column; gap: 150px; }

/* 1. Profile Section Style */
.profile-hero { display: flex; align-items: center; gap: 60px; padding: 60px; }
.story-content { flex: 1; }
.photo-container { flex: 0.8; display: flex; justify-content: center; }
.photo-frame { padding: 15px; background: white; border-radius: 40px; box-shadow: 0 20px 40px rgba(0,0,0,0.1); border: 1px solid var(--border-glass); }
.profile-photo { width: 320px; height: 320px; object-fit: cover; border-radius: 30px; }
.section-text-large { font-size: 1.3rem; color: var(--text-muted); line-height: 1.8; margin-top: 20px; }

/* 2. About & Journey Style */
.full-card { padding: 60px; }
.bio-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 60px; margin-top: 40px; }
.bio-text h4, .education-timeline h4 { font-size: 1.4rem; border-bottom: 2px solid var(--accent-1); display: inline-block; margin-bottom: 25px; padding-bottom: 5px; }
.bio-text p { font-size: 1.1rem; color: var(--text-muted); line-height: 1.9; }

.timeline-v2 { display: flex; flex-direction: column; gap: 30px; }
.t-item { position: relative; padding-left: 30px; border-left: 2px solid var(--accent-1); }
.t-year { color: var(--accent-1); font-weight: 800; font-size: 0.9rem; display: block; margin-bottom: 5px; }
.t-item h5 { font-size: 1.15rem; }
.t-item p { color: var(--text-muted); font-size: 0.95rem; }

/* 3. Projects Grid Style */
.project-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 30px; margin-top: 40px; }
.project-item { padding: 0; overflow: hidden; transition: all 0.4s; cursor: pointer; }
.project-thumb { height: 240px; overflow: hidden; background: #dfe7ed; }
.project-thumb img { width: 100%; height: 100%; object-fit: cover; transition: transform 0.6s; }
.project-info { padding: 30px; }
.project-item:hover { transform: translateY(-10px); box-shadow: 0 20px 40px rgba(0,0,0,0.1); }
.project-item:hover .project-thumb img { transform: scale(1.1); }

/* 4. Contact Section Style */
.contact-card { padding: 80px; text-align: center; }
.contact-links { display: flex; justify-content: center; gap: 30px; margin-top: 40px; }
.c-link { padding: 15px 30px; background: white; border-radius: 12px; font-weight: 700; transition: all 0.3s; border: 1.5px solid var(--text-main); }
.c-link:hover { background: var(--text-main); color: white; transform: translateY(-5px); }

.section-badge { background: var(--text-main); color: white; padding: 6px 16px; border-radius: 50px; font-size: 0.8rem; font-weight: 600; display: inline-block; margin-bottom: 15px; }
.title-sub { font-size: 2rem; font-weight: 800; }
.centered { text-align: center; }

@keyframes fadeIn { 
  from { opacity: 0; } 
  to { opacity: 1; } 
}

@media (max-width: 1024px) {
  .profile-hero, .bio-grid { flex-direction: column; grid-template-columns: 1fr; text-align: center; }
  .photo-container { margin-top: 30px; }
  .timeline-v2 { text-align: left; }
}
</style>
