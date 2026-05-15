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
                <a href="mailto:rio.saputra@example.com">rio.saputra@example.com</a>
              </div>
            </div>
            <div class="info-item">
              <span class="icon">📱</span>
              <div>
                <h4>WhatsApp</h4>
                <a href="https://wa.me/6281234567890" target="_blank">+62 812-3456-7890</a>
              </div>
            </div>
            <div class="info-item">
              <span class="icon">📍</span>
              <div>
                <h4>Location</h4>
                <span>Indonesia</span>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <a href="https://github.com" target="_blank" class="social-btn" title="GitHub">GH</a>
            <a href="https://linkedin.com" target="_blank" class="social-btn" title="LinkedIn">IN</a>
            <a href="https://wa.me/6281234567890" target="_blank" class="social-btn" title="WhatsApp">WA</a>
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
