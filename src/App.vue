<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import Hero from './components/Hero.vue';
import About from './components/About.vue';
import Experience from './components/Experience.vue';
import Projects from './components/Projects.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';

const isScrolled = ref(false);
const isMenuOpen = ref(false);
const activeSection = ref('home');

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  // Prevent body scroll when menu is open
  document.body.style.overflow = isMenuOpen.value ? 'hidden' : '';
};

const closeMenu = () => {
  isMenuOpen.value = false;
  document.body.style.overflow = '';
};

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
        
        <!-- Mobile Menu Toggle -->
        <button class="mobile-menu-btn" @click="toggleMenu" :class="{ 'menu-open': isMenuOpen }">
          <span></span>
          <span></span>
          <span></span>
        </button>

        <!-- Mobile Nav Drawer -->
        <div class="mobile-nav" :class="{ 'mobile-nav-active': isMenuOpen }">
          <div class="mobile-nav-links">
            <a href="#home" @click="closeMenu" :class="{ active: activeSection === 'home' }">Home</a>
            <a href="#about" @click="closeMenu" :class="{ active: activeSection === 'about' }">About</a>
            <a href="#experience" @click="closeMenu" :class="{ active: activeSection === 'experience' }">Organization</a>
            <a href="#projects" @click="closeMenu" :class="{ active: activeSection === 'projects' }">Projects</a>
            <a href="#contact" @click="closeMenu" :class="{ active: activeSection === 'contact' }">Contact</a>
          </div>
        </div>
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
    
    <Footer />
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

@media (max-width: 768px) {
  .desktop-nav {
    display: none;
  }
  
  .mobile-menu-btn {
    display: flex;
    flex-direction: column;
    gap: 6px;
    z-index: 101;
  }

  .mobile-menu-btn span {
    width: 30px;
    height: 2px;
    background-color: var(--color-text-main);
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  }

  .mobile-menu-btn.menu-open span:nth-child(1) {
    transform: translateY(8px) rotate(45deg);
  }

  .mobile-menu-btn.menu-open span:nth-child(2) {
    opacity: 0;
  }

  .mobile-menu-btn.menu-open span:nth-child(3) {
    transform: translateY(-8px) rotate(-45deg);
  }

  .mobile-nav {
    position: fixed;
    top: 0;
    right: -100%;
    width: 100%;
    height: 100vh;
    background: rgba(15, 17, 21, 0.95);
    backdrop-filter: blur(10px);
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
    z-index: 100;
  }

  .mobile-nav-active {
    right: 0;
  }

  .mobile-nav-links {
    display: flex;
    flex-direction: column;
    gap: 2.5rem;
    text-align: center;
  }

  .mobile-nav-links a {
    font-size: 1.8rem;
    font-family: var(--font-heading);
    font-weight: 700;
    color: var(--color-text-muted);
    transition: all 0.3s ease;
  }

  .mobile-nav-links a:hover,
  .mobile-nav-links a.active {
    color: var(--color-primary);
    transform: scale(1.1);
  }
}
</style>
