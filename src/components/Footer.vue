<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="footer">
    <div class="footer-wave">
      <svg data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M321.39,56.44c58-10.79,114.16-30.13,172-41.86,82.39-16.72,168.19-17.73,250.45-.39C823.78,31,906.67,72,985.66,92.83c70.05,18.48,146.53,26.09,214.34,3V0H0V27.35A600.21,600.21,0,0,0,321.39,56.44Z" class="shape-fill"></path>
      </svg>
    </div>

    <div class="container footer-grid">
      <div class="footer-brand">
        <a href="#home" class="logo">RS<span>.</span></a>
        <p class="brand-description">
          A passionate software developer specialized in building modern, 
          performant, and beautiful web applications that provide exceptional user experiences.
        </p>
        <div class="social-links">
          <a href="https://github.com/rioohoo12" target="_blank" class="social-icon" aria-label="GitHub">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.28 1.15-.28 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path><path d="M9 18c-4.51 2-5-2-7-2"></path></svg>
          </a>
          <a href="https://www.linkedin.com/in/rio-saputra-situmorang-a56727367/" target="_blank" class="social-icon" aria-label="LinkedIn">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect width="4" height="12" x="2" y="9"></rect><circle cx="4" cy="4" r="2"></circle></svg>
          </a>
          <a href="https://www.instagram.com/_rio176?igsh=MTV2bzBteXVubzhyOQ==" target="_blank" class="social-icon" aria-label="Instagram">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"></line></svg>
          </a>
          <a href="https://wa.me/6287861510691" target="_blank" class="social-icon" aria-label="WhatsApp">
            <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
          </a>
        </div>
      </div>

      <div class="footer-nav">
        <h4>Navigation</h4>
        <ul>
          <li><a href="#home">Home</a></li>
          <li><a href="#about">About Me</a></li>
          <li><a href="#experience">Organization</a></li>
          <li><a href="#projects">Project Section</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>

      <div class="footer-contact">
        <h4>Contact Me</h4>
        <ul>
          <li>
            <span class="contact-label">Email:</span>
            <a href="mailto:rioosaputraa1412@gmail.com">rioosaputraa1412@gmail.com</a>
          </li>
          <li>
            <span class="contact-label">Location:</span>
            <span>Tangerang, Indonesia</span>
          </li>
        </ul>
      </div>
    </div>

    <div class="footer-bottom">
      <div class="container bottom-content">
        <p>&copy; {{ currentYear }} Rio Saputra. All rights reserved.</p>
        <p class="credit">
          Designed with <span class="heart">♥</span> by Rio
        </p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  position: relative;
  background: var(--color-surface);
  padding-top: 100px;
  margin-top: 80px;
  overflow: hidden;
}

.footer-wave {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  overflow: hidden;
  line-height: 0;
}

.footer-wave svg {
  position: relative;
  display: block;
  width: calc(134% + 1.3px);
  height: 60px;
}

.footer-wave .shape-fill {
  fill: var(--color-bg);
}

.footer-grid {
  display: grid;
  grid-template-columns: 2fr 1fr 1.5fr;
  gap: 4rem;
  padding-bottom: 4rem;
}

.logo {
  font-family: var(--font-heading);
  font-size: 2rem;
  font-weight: 800;
  color: var(--color-text-main);
  text-decoration: none;
  margin-bottom: 1.5rem;
  display: inline-block;
}

.logo span {
  color: var(--color-primary);
}

.brand-description {
  color: var(--color-text-muted);
  line-height: 1.7;
  margin-bottom: 2rem;
  max-width: 400px;
}

.social-links {
  display: flex;
  gap: 1.2rem;
}

.social-icon {
  width: 45px;
  height: 45px;
  border-radius: 12px;
  background: rgba(255, 255, 255, 0.03);
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--color-text-muted);
  border: 1px solid rgba(255, 255, 255, 0.08);
  transition: all 0.3s ease;
}

.social-icon:hover {
  background: var(--color-primary);
  color: white;
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(236, 72, 153, 0.2);
  border-color: var(--color-primary);
}

.footer-nav h4,
.footer-contact h4 {
  font-size: 1.2rem;
  color: var(--color-text-main);
  margin-bottom: 1.5rem;
  position: relative;
}

.footer-nav h4::after,
.footer-contact h4::after {
  content: '';
  position: absolute;
  bottom: -8px;
  left: 0;
  width: 30px;
  height: 2px;
  background: var(--color-primary);
}

.footer-nav ul,
.footer-contact ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-nav li,
.footer-contact li {
  margin-bottom: 1rem;
}

.footer-nav a {
  color: var(--color-text-muted);
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-nav a:hover {
  color: var(--color-primary);
  padding-left: 5px;
}

.contact-label {
  display: block;
  font-size: 0.8rem;
  color: var(--color-primary);
  margin-bottom: 0.2rem;
  font-weight: 600;
  text-transform: uppercase;
}

.footer-contact a,
.footer-contact span {
  color: var(--color-text-muted);
  text-decoration: none;
}

.footer-contact a:hover {
  color: var(--color-primary);
}

.footer-bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.05);
  padding: 2rem 0;
  background: rgba(0, 0, 0, 0.2);
}

.bottom-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: var(--color-text-muted);
  font-size: 0.9rem;
}

.heart {
  color: #ef4444;
  display: inline-block;
  animation: heartbeat 1.5s infinite;
}

@keyframes heartbeat {
  0% { transform: scale(1); }
  50% { transform: scale(1.2); }
  100% { transform: scale(1); }
}

@media (max-width: 992px) {
  .footer-grid {
    grid-template-columns: 1fr 1fr;
  }
  .footer-brand {
    grid-column: span 2;
  }
}

@media (max-width: 576px) {
  .footer-grid {
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }
  .footer-brand {
    grid-column: span 1;
  }
  .bottom-content {
    flex-direction: column;
    gap: 1rem;
    text-align: center;
  }
}
</style>
