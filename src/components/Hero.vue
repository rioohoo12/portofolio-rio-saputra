<script setup>
import { onMounted, ref } from 'vue';

const isVisible = ref(false);

onMounted(() => {
  setTimeout(() => {
    isVisible.value = true;
  }, 100);
});
</script>

<template>
  <section id="home" class="hero section-padding">
    <div class="container hero-container" :class="{ 'is-visible': isVisible }">
      <div class="hero-content">
        <h2 class="greeting">Hi, I'm</h2>
        <h1 class="name">Rio Saputra</h1>
        <h3 class="role">Front-End Developer & IT Support Enthusiast</h3>
        <p class="description">
          Passionate about building responsive and user-friendly web applications.
          I enjoy creating clean interfaces and solving technical problems.
        </p>
        <div class="cta-group">
          <a href="#projects" class="btn-primary">View My Work</a>
          <a href="#contact" class="btn-secondary">Contact Me</a>
        </div>
      </div>
      <div class="hero-visual">
        <div class="blob-shape"></div>
        <div class="profile-placeholder">
           <!-- Placeholder for a real image, styled beautifully -->
           <div class="code-icon">&lt;/&gt;</div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding-top: 8rem; /* Account for navbar */
}

.hero::before {
  content: '';
  position: absolute;
  top: -20%;
  left: -10%;
  width: 50vw;
  height: 50vw;
  background: radial-gradient(circle, var(--color-primary-glow) 0%, transparent 70%);
  z-index: -1;
  filter: blur(80px);
  opacity: 0.5;
}

.hero-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 1s ease, transform 1s ease;
}

.hero-container.is-visible {
  opacity: 1;
  transform: translateY(0);
}

.greeting {
  color: var(--color-secondary);
  font-family: var(--font-primary);
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.5rem;
  letter-spacing: 2px;
  text-transform: uppercase;
}

.name {
  font-size: 4.5rem;
  margin-bottom: 0.5rem;
  background: linear-gradient(to right, #fff, #94a3b8);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.role {
  font-size: 2rem;
  color: var(--color-text-muted);
  margin-bottom: 1.5rem;
}

.description {
  font-size: 1.1rem;
  color: var(--color-text-muted);
  max-width: 500px;
  margin-bottom: 2.5rem;
}

.cta-group {
  display: flex;
  gap: 1.5rem;
}

.btn-secondary {
  display: inline-block;
  padding: 0.8rem 2rem;
  background: transparent;
  color: var(--color-text-main);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 2rem;
  font-weight: 600;
  transition: all var(--transition-normal);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.05);
  border-color: var(--color-primary);
  color: var(--color-primary);
}

.hero-visual {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.blob-shape {
  position: absolute;
  width: 400px;
  height: 400px;
  background: linear-gradient(135deg, var(--color-primary), var(--color-secondary));
  border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%;
  animation: morph 8s ease-in-out infinite;
  opacity: 0.2;
  filter: blur(20px);
  z-index: 0;
}

.profile-placeholder {
  width: 320px;
  height: 400px;
  background: var(--glass-bg);
  backdrop-filter: blur(10px);
  border: var(--glass-border);
  border-radius: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
  position: relative;
  overflow: hidden;
  transform: rotate(3deg);
  transition: transform 0.5s ease;
}

.profile-placeholder:hover {
  transform: rotate(0deg) scale(1.02);
}

.code-icon {
  font-size: 5rem;
  font-family: var(--font-heading);
  font-weight: 800;
  background: linear-gradient(to right, var(--color-primary), var(--color-secondary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

@keyframes morph {
  0%, 100% { border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%; }
  34% { border-radius: 70% 30% 50% 50% / 30% 30% 70% 70%; }
  67% { border-radius: 100% 60% 60% 100% / 100% 100% 60% 60%; }
}

@media (max-width: 992px) {
  .hero-container {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 3rem;
  }
  
  .description {
    margin: 0 auto 2.5rem auto;
  }
  
  .cta-group {
    justify-content: center;
  }
  
  .name {
    font-size: 3.5rem;
  }
  
  .hero-visual {
    order: -1;
  }
}

@media (max-width: 576px) {
  .name { font-size: 2.5rem; }
  .role { font-size: 1.5rem; }
  .profile-placeholder { width: 260px; height: 320px; }
  .cta-group { flex-direction: column; }
}
</style>
