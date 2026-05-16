<script setup>
const getAssetUrl = (name) => {
  const fileName = name.split('/').pop();
  return new URL(`../assets/${fileName}`, import.meta.url).href;
};

const experiences = [
  {
    id: 1,
    role: 'Staff of Event Division (Class of 2023)',
    company: 'HIMA Faculty of Technology Information',
    duration: '2023 - 2027',
    images: ['staff-2023.jpeg'],
    description: [
      'Contributed to the planning and coordination of various organizational events and programs within a large team of over 100 members.',
      'Assisted in managing logistics, schedules, and on-site execution to ensure successful event outcomes for the 2023 cohort.',
      'Collaborated with team members to brainstorm creative concepts and engagement strategies for students.'
    ]
  },
  {
    id: 2,
    role: 'Event Division Member',
    company: 'HIMA Faculty of Technology Information',
    duration: '2025 - 2027',
    images: ['hima-1.jpeg', 'hima-2.jpeg', 'hima-3.jpeg'],
    description: [
      'Planned and managed faculty-wide technology events, including the "Ekskursi Trans Studio Bandung" program.',
      'Led event execution and public speaking roles, ensuring clear communication and program flow.',
      'Collaborated closely with design and technical teams to build responsive event landing pages and registration interfaces.'
    ]
  }
];

</script>

<template>
  <section id="experience" class="experience section-padding">
    <div class="container">
      <h2 class="section-title">Organization Experience</h2>
      
      <div class="experience-timeline">
        <div v-for="exp in experiences" :key="exp.id" class="timeline-item glass-card">
          <div class="timeline-dot"></div>
          <div class="timeline-content">
            <div class="timeline-header">
              <h3>{{ exp.role }}</h3>
            </div>
            <h4 class="company">{{ exp.company }}</h4>
            
            <div v-if="exp.images && exp.images.length" class="experience-gallery">
              <div v-for="(img, idx) in exp.images" :key="idx" class="experience-image-container">
                <img :src="getAssetUrl(img)" :alt="exp.role" class="experience-image" />
              </div>
            </div>

            <ul class="responsibilities">
              <li v-for="(task, index) in exp.description" :key="index">
                {{ task }}
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.experience-timeline {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
}

/* Vertical line */
.experience-timeline::before {
  content: '';
  position: absolute;
  top: 0;
  left: 20px; /* Adjust based on dot size */
  height: 100%;
  width: 2px;
  background: rgba(255, 255, 255, 0.1);
}

.timeline-item {
  position: relative;
  margin-bottom: 2.5rem;
  padding: 2rem 2rem 2rem 4rem; /* Extra left padding for dot and line */
  margin-left: 10px;
}

.timeline-item:last-child {
  margin-bottom: 0;
}

.timeline-dot {
  position: absolute;
  left: 3px;
  top: 2.5rem;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  background: var(--color-primary);
  box-shadow: 0 0 10px var(--color-primary-glow);
  z-index: 1;
}

.timeline-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: 1rem;
  margin-bottom: 0.5rem;
}

.timeline-header h3 {
  font-size: 1.4rem;
  color: var(--color-text-main);
  margin: 0;
}

.duration {
  font-size: 0.9rem;
  padding: 0.3rem 0.8rem;
  background: rgba(236, 72, 153, 0.1);
  color: var(--color-secondary);
  border-radius: 2rem;
  font-weight: 500;
}

.company {
  font-size: 1.1rem;
  color: var(--color-primary);
  margin-bottom: 1.5rem;
  font-weight: 500;
}

.responsibilities {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.responsibilities li {
  position: relative;
  padding-left: 1.5rem;
  margin-bottom: 0.8rem;
  color: var(--color-text-muted);
  line-height: 1.6;
}

.responsibilities li::before {
  content: '▹';
  position: absolute;
  left: 0;
  color: var(--color-primary);
  font-size: 1.2rem;
}

.experience-gallery {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1rem;
  margin: 1rem 0 1.5rem 0;
}

.experience-image-container {
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  aspect-ratio: 16 / 9;
}

.experience-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.5s ease;
}

.experience-image:hover {
  transform: scale(1.03);
}

@media (max-width: 576px) {
  .experience-timeline::before {
    left: 15px;
  }
  
  .timeline-item {
    padding: 1.5rem 1.5rem 1.5rem 3rem;
  }
  
  .timeline-dot {
    left: -1px;
    top: 2rem;
  }
  
  .timeline-header {
    flex-direction: column;
    gap: 0.5rem;
  }
}
</style>
