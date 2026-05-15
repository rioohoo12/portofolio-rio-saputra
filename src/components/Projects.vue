<script setup>
const projects = [
  {
    id: 1,
    title: 'Rent Car Web',
    description: 'A comprehensive car rental platform developed as a final project for Web 2, utilizing React.js for the frontend, Nest.js for the backend, and PostgreSQL for the database.',
    tags: ['React.js', 'Nest.js', 'PostgreSQL'],
    images: ['/src/assets/rent-car.png'],
    link: '#'
  },
  {
    id: 2,
    title: 'Chairman of the Alumni Homecoming Event',
    description: 'Served as the Chairman of the Committee for the Alumni Homecoming event, which focused on strengthening professional and personal bonds among the alumni community.',
    tags: ['Leadership', 'Event Planning', 'Coordination'],
    images: ['/src/assets/123.jpeg', '/src/assets/pp.jpeg'],
    link: '#'
  },
  {
    id: 3,
    title: 'Sabbath School Speaker',
    description: 'Selected by the Sabbath School staff to present educational materials, I accepted this role to refine my public speaking skills and build confidence in addressing large audiences.',
    tags: ['Public Speaking', 'Leadership', 'Communication'],
    video: '/src/assets/sabbath-speaker.mp4',
    images: [],
    link: '#'
  },
  {
    id: 4,
    title: "2nd Place in the 2026 'Discus 3.0' Debate",
    description: 'Representing the Faculty of Information Technology, our team of three secured 2nd place. This achievement honed our collaboration skills, goal-oriented leadership, and effective communication.',
    tags: ['Debate', 'Teamwork', 'Public Speaking'],
    images: ['/src/assets/234.jpeg', '/src/assets/345.jpeg'],
    link: '#'
  },
  {
    id: 5,
    title: 'Undergraduate Thesis Research',
    description: 'Developed a comprehensive system architecture using Vue.js for the frontend and Laravel for the backend as part of my undergraduate thesis research.',
    tags: ['Vue.js', 'Laravel', 'System Design'],
    images: ['/src/assets/jurnal.png'],
    link: '#'
  }
];
</script>

<template>
  <section id="projects" class="projects section-padding">
    <div class="container">
      <h2 class="section-title">Project Section</h2>
      
      <div class="projects-grid">
        <div v-for="project in projects" :key="project.id" class="project-card glass-card">
          <div class="project-media-container" :class="{ 'multi-image': project.images && project.images.length > 1 }">
            <div v-if="project.video" class="project-video-wrapper">
              <video :src="project.video" controls class="project-video"></video>
            </div>
            <template v-else>
              <div v-for="(img, idx) in project.images" :key="idx" class="project-image">
                <img :src="img" :alt="project.title">
                <div class="project-overlay">
                  <a :href="project.link" class="btn-primary" target="_blank">View Project</a>
                </div>
              </div>
            </template>
          </div>
          <div class="project-info">
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="project-tags">
              <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2.5rem;
}

.project-card {
  padding: 0;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.project-image {
  position: relative;
  width: 100%;
  height: 240px;
  overflow: hidden;
}

.project-media-container.multi-image {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2px;
}

.project-media-container.multi-image .project-image {
  height: 180px;
}

.project-video-wrapper {
  width: 100%;
  height: 240px;
  background: #000;
}

.project-video {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.project-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform var(--transition-slow);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(15, 17, 21, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  transition: opacity var(--transition-normal);
  backdrop-filter: blur(4px);
}

.project-card:hover .project-image img {
  transform: scale(1.1);
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-info {
  padding: 1.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.project-info h3 {
  font-size: 1.4rem;
  margin-bottom: 0.8rem;
  color: var(--color-text-main);
}

.project-info p {
  color: var(--color-text-muted);
  font-size: 0.95rem;
  margin-bottom: 1.5rem;
  flex: 1;
}

.project-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag {
  font-size: 0.8rem;
  padding: 0.3rem 0.8rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 2rem;
  color: var(--color-secondary);
}
</style>
