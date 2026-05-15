<script setup>
const frontendSkills = [
  'HTML5', 'CSS3', 'JavaScript', 'Vue.js', 'React.js', 
  'Tailwind CSS', 'Responsive Web Design', 'REST API Integration', 'Git & GitHub'
];

const itSupportSkills = [
  'Hardware & Software Troubleshooting', 'Windows & Basic Linux', 
  'Network Basics', 'Technical Support', 'System Maintenance'
];

const otherSkills = [
  'Problem Solving', 'Team Collaboration', 'Technical Documentation', 'Time Management'
];
</script>

<template>
  <section id="about" class="about section-padding">
    <div class="container">
      <h2 class="section-title">About Me</h2>
      
      <div class="about-content">
        <div class="about-text glass-card">
          <h3>Get to know me</h3>
          <p>
            I am a Computer Engineering student with a strong interest in Front-End Development and IT Support. I have experience developing responsive and user-friendly web interfaces using modern web technologies while also handling basic technical troubleshooting and system support.
          </p>
          <p>
            Through my academic projects and 3-month internship experience, I improved my skills in problem-solving, teamwork, and adapting to new technologies quickly. I am passionate about building efficient digital solutions, improving user experiences, and continuously growing both my technical and analytical abilities.
          </p>
        </div>
        
        <div class="skills-wrapper glass-card">
          <h3>My Skills</h3>
          
          <div class="skill-category">
            <h4>💻 Front-End Skills</h4>
            <div class="tags-container">
              <span v-for="skill in frontendSkills" :key="skill" class="skill-tag">{{ skill }}</span>
            </div>
          </div>

          <div class="skill-category">
            <h4>🛠 IT Support Skills</h4>
            <div class="tags-container">
              <span v-for="skill in itSupportSkills" :key="skill" class="skill-tag">{{ skill }}</span>
            </div>
          </div>

          <div class="skill-category">
            <h4>📊 Other Skills</h4>
            <div class="tags-container">
              <span v-for="skill in otherSkills" :key="skill" class="skill-tag">{{ skill }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  position: relative;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 3rem;
}

.about-text h3, .skills-wrapper h3 {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
  color: var(--color-primary);
}

.about-text p {
  margin-bottom: 1rem;
  color: var(--color-text-muted);
  font-size: 1.1rem;
  line-height: 1.8;
}

.skill-category {
  margin-bottom: 2rem;
}

.skill-category:last-child {
  margin-bottom: 0;
}

.skill-category h4 {
  font-size: 1.2rem;
  margin-bottom: 1rem;
  color: var(--color-text-main);
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.tags-container {
  display: flex;
  flex-wrap: wrap;
  gap: 0.8rem;
}

.skill-tag {
  padding: 0.5rem 1rem;
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.2);
  border-radius: 2rem;
  font-size: 0.9rem;
  color: var(--color-text-main);
  transition: all var(--transition-fast);
}

.skill-tag:hover {
  background: var(--color-primary);
  border-color: var(--color-primary);
  transform: translateY(-2px);
}

@media (max-width: 992px) {
  .about-content {
    grid-template-columns: 1fr;
  }
}
</style>
