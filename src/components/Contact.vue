<script setup>
import { ref } from 'vue';

const form = ref({
  name: '',
  email: '',
  message: ''
});

const isSubmitting = ref(false);
const submitted = ref(false);

const handleSubmit = (e) => {
  e.preventDefault();
  isSubmitting.value = true;
  
  // Simulate API call
  setTimeout(() => {
    isSubmitting.value = false;
    submitted.value = true;
    form.value = { name: '', email: '', message: '' };
    
    // Reset success message after 3 seconds
    setTimeout(() => {
      submitted.value = false;
    }, 3000);
  }, 1500);
};
</script>

<template>
  <section id="contact" class="contact section-padding">
    <div class="container">
      <h2 class="section-title">Get In Touch</h2>
      
      <div class="contact-content">
        <div class="contact-info glass-card">
          <h3>Let's talk about your project</h3>
          <p>
            Feel free to reach out for collaborations, job opportunities, 
            or just to say hi! I'm always open to discussing new projects 
            and creative ideas.
          </p>
          
          <div class="info-items">
            <div class="info-item">
              <span class="icon">✉</span>
              <div>
                <h4>Email</h4>
                <a href="mailto:rioosaputraa1412@gmail.com">rioosaputraa1412@gmail.com</a>
              </div>
            </div>
            <div class="info-item">
              <span class="icon">📱</span>
              <div>
                <h4>WhatsApp</h4>
                <a href="https://wa.me/6287861510691" target="_blank">+62 878-6151-0691</a>
              </div>
            </div>
            <div class="info-item">
              <span class="icon">📍</span>
              <div>
                <h4>Location</h4>
                <span>Tangerang</span>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <a href="https://github.com/rioohoo12" target="_blank" class="social-btn" title="GitHub">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M15 22v-4a4.8 4.8 0 0 0-1-3.5c3 0 6-2 6-5.5.08-1.25-.27-2.48-1-3.5.28-1.15.28-2.35 0-3.5 0 0-1 0-3 1.5-2.64-.5-5.36-.5-8 0C6 2 5 2 5 2c-.28 1.15-.28 2.35 0 3.5A5.403 5.403 0 0 0 4 9c0 3.5 3 5.5 6 5.5-.39.49-.68 1.05-.85 1.65-.17.6-.22 1.23-.15 1.85v4"></path><path d="M9 18c-4.51 2-5-2-7-2"></path></svg>
            </a>
            <a href="https://www.linkedin.com/in/rio-saputra-situmorang-a56727367/" target="_blank" class="social-btn" title="LinkedIn">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect width="4" height="12" x="2" y="9"></rect><circle cx="4" cy="4" r="2"></circle></svg>
            </a>
            <a href="https://www.instagram.com/_rio176?igsh=MTV2bzBteXVubzhyOQ==" target="_blank" class="social-btn" title="Instagram">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"></line></svg>
            </a>
            <a href="https://wa.me/6287861510691" target="_blank" class="social-btn" title="WhatsApp">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
            </a>
          </div>
        </div>
        
        <form @submit="handleSubmit" class="contact-form glass-card">
          <div class="form-group">
            <label for="name">Name</label>
            <input type="text" id="name" v-model="form.name" required placeholder="John Doe">
          </div>
          
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" v-model="form.email" required placeholder="john@example.com">
          </div>
          
          <div class="form-group">
            <label for="message">Message</label>
            <textarea id="message" v-model="form.message" rows="5" required placeholder="Tell me about your project..."></textarea>
          </div>
          
          <button type="submit" class="btn-primary submit-btn" :disabled="isSubmitting">
            <span v-if="isSubmitting">Sending...</span>
            <span v-else>Send Message</span>
          </button>
          
          <p v-if="submitted" class="success-message">
            Thanks! Your message has been sent successfully.
          </p>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-content {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 3rem;
}

.contact-info h3 {
  font-size: 1.8rem;
  margin-bottom: 1rem;
  color: var(--color-primary);
}

.contact-info p {
  color: var(--color-text-muted);
  margin-bottom: 2rem;
}

.info-items {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin-bottom: 2.5rem;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.icon {
  font-size: 1.5rem;
  color: var(--color-secondary);
}

.info-item h4 {
  font-size: 1rem;
  color: var(--color-text-main);
  margin-bottom: 0.2rem;
}

.info-item a, .info-item span {
  color: var(--color-text-muted);
  font-size: 0.9rem;
}

.info-item a:hover {
  color: var(--color-primary);
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-btn {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.05);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 0.9rem;
  font-weight: 600;
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: all var(--transition-fast);
}

.social-btn:hover {
  background: var(--color-primary);
  border-color: var(--color-primary);
  transform: translateY(-3px);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.form-group {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

label {
  font-size: 0.9rem;
  font-weight: 500;
  color: var(--color-text-main);
}

input, textarea {
  width: 100%;
  padding: 1rem;
  background: rgba(0, 0, 0, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 0.5rem;
  color: var(--color-text-main);
  font-family: inherit;
  transition: border-color var(--transition-fast);
}

input:focus, textarea:focus {
  outline: none;
  border-color: var(--color-primary);
  background: rgba(0, 0, 0, 0.3);
}

.submit-btn {
  width: 100%;
  margin-top: 1rem;
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.success-message {
  margin-top: 1rem;
  color: #10b981;
  text-align: center;
  font-size: 0.9rem;
}

@media (max-width: 992px) {
  .contact-content {
    grid-template-columns: 1fr;
  }
}
</style>
