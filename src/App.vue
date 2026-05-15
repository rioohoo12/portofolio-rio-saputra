<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Experience from './components/Experience.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';

const isScrolled = ref(false);
const activeSection = ref('home');

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50;
  
  // Highlight active nav item based on scroll position
  const sections = ['home', 'about', 'experience', 'projects', 'contact'];
  const scrollPosition = window.scrollY + 200; // offset
  
  for (const section of sections) {
    const el = document.getElementById(section);
    if (el) {
      const top = el.offsetTop;
      const height = el.offsetHeight;
      if (scrollPosition >= top && scrollPosition < top + height) {
        activeSection.value = section;
      }
    }
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <div class="app-wrapper">
    <!-- Navbar -->
    <header class="navbar" :class="{ 'navbar-scrolled': isScrolled }">
      <div class="nav-container">
        <a href="#home" class="logo">RS.</a>
        
        <nav class="nav-links desktop-nav">
          <a href="#home" :class="{ active: activeSection === 'home' }">Home</a>
          <a href="#about" :class="{ active: activeSection === 'about' }">About</a>
          <a href="#experience" :class="{ active: activeSection === 'experience' }">Organization</a>
          <a href="#projects" :class="{ active: activeSection === 'projects' }">Projects</a>
          <a href="#contact" :class="{ active: activeSection === 'contact' }">Contact</a>
        </nav>
        
        <!-- Mobile menu button placeholder (could be expanded later) -->
        <button class="mobile-menu-btn">
          <span></span>
          <span></span>
          <span></span>
        </button>
      </div>
    </header>

    <!-- Main Content -->
    <main>
      <Hero />
      <About />
      <Experience />
      <Projects />
      <Contact />
    </main>
    
    <!-- Footer -->
    <footer class="footer">
      <div class="footer-glow"></div>
      <div class="container footer-content">
        <div class="footer-brand">
          <a href="#home" class="logo logo-large">RS.</a>
          <p class="footer-tagline">Building responsive and user-friendly web applications.</p>
        </div>
        
        <div class="footer-links">
          <a href="#home">Home</a>
          <a href="#about">About</a>
          <a href="#experience">Organization</a>
          <a href="#projects">Projects</a>
          <a href="#contact">Contact</a>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; {{ new Date().getFullYear() }} Rio Saputra Situmorang. All rights reserved.</p>
        <p class="built-with">
          Designed & Built with <span class="heart">♥</span> using Vue.js & Vanilla CSS
        </p>
      </div>
    </footer>
  </div>
</template>

<style scoped>
.app-wrapper {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

/* Navbar */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 1.5rem 0;
  z-index: 100;
  transition: all var(--transition-normal);
  background: transparent;
}

.navbar-scrolled {
  padding: 1rem 0;
  background: rgba(15, 17, 21, 0.8);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 800;
  color: var(--color-text-main);
  background: linear-gradient(to right, var(--color-primary), var(--color-secondary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.nav-links {
  display: flex;
  gap: 2rem;
}

.nav-links a {
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--color-text-muted);
  position: relative;
}

.nav-links a:hover,
.nav-links a.active {
  color: var(--color-text-main);
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--color-primary);
  transition: width var(--transition-fast);
}

.nav-links a:hover::after,
.nav-links a.active::after {
  width: 100%;
}

.mobile-menu-btn {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: transparent;
  border: none;
  cursor: pointer;
}

.mobile-menu-btn span {
  width: 25px;
  height: 2px;
  background-color: var(--color-text-main);
  transition: all 0.3s;
}

main {
  flex: 1;
}

/* Footer */
.footer {
  position: relative;
  padding: 4rem 0 0 0;
  background: var(--color-surface);
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  margin-top: 6rem;
  overflow: hidden;
}

.footer-glow {
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60%;
  height: 100px;
  background: radial-gradient(ellipse at top, var(--color-primary-glow), transparent 70%);
  opacity: 0.5;
  pointer-events: none;
}

.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 2rem;
  padding-bottom: 3rem;
}

.footer-brand .logo-large {
  font-size: 2rem;
  margin-bottom: 0.5rem;
  display: inline-block;
}

.footer-tagline {
  color: var(--color-text-muted);
  max-width: 300px;
  line-height: 1.6;
}

.footer-links {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.footer-links a {
  color: var(--color-text-main);
  font-weight: 500;
  position: relative;
}

.footer-links a:hover {
  color: var(--color-primary);
}

.footer-bottom {
  padding: 1.5rem 2rem;
  background: rgba(0, 0, 0, 0.3);
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-bottom p {
  color: var(--color-text-muted);
  font-size: 0.9rem;
  margin: 0;
}

.built-with {
  opacity: 0.8;
}

.heart {
  color: var(--color-secondary);
  display: inline-block;
  animation: heartbeat 1.5s infinite;
}

@keyframes heartbeat {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.2); }
}

@media (max-width: 768px) {
  .desktop-nav {
    display: none;
  }
  
  .mobile-menu-btn {
    display: flex;
  }
  
  .footer-content {
    flex-direction: column;
    text-align: center;
  }
  
  .footer-bottom {
    flex-direction: column;
    text-align: center;
  }
}
</style>
