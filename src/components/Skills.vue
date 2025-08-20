<template>
  <section id="skills" class="skills">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Skills & Technologies</h2>
        <p class="section-subtitle">Technologies and tools I've learned in web development</p>
      </div>

      <div class="skills-grid">
        <!-- Frontend Skills -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">🎨</span>
            Frontend Development
          </h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in frontendSkills" :key="skill.name">
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-percentage">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div 
                  class="skill-progress" 
                  :style="{ width: skill.level + '%', backgroundColor: skill.color }"
                ></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Backend Skills -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">⚙️</span>
            Backend Development
          </h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in backendSkills" :key="skill.name">
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-percentage">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div 
                  class="skill-progress" 
                  :style="{ width: skill.level + '%', backgroundColor: skill.color }"
                ></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Tools & Others -->
        <div class="skill-category">
          <h3 class="category-title">
            <span class="category-icon">🛠️</span>
            Tools & Others
          </h3>
          <div class="skills-list">
            <div class="skill-item" v-for="skill in toolsSkills" :key="skill.name">
              <div class="skill-info">
                <span class="skill-name">{{ skill.name }}</span>
                <span class="skill-percentage">{{ skill.level }}%</span>
              </div>
              <div class="skill-bar">
                <div 
                  class="skill-progress" 
                  :style="{ width: skill.level + '%', backgroundColor: skill.color }"
                ></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Technology Icons -->
      <div class="tech-showcase">
        <h3>Technologies I Use</h3>
        <div class="tech-grid">
          <div class="tech-item" v-for="tech in technologies" :key="tech.name">
            <div class="tech-icon" :style="{ backgroundColor: tech.color }">
              {{ tech.icon }}
            </div>
            <span class="tech-name">{{ tech.name }}</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'SkillsSection',
  data() {
    return {
      frontendSkills: [
        { name: 'HTML5', level: 95, color: '#e34f26' },
        { name: 'CSS3', level: 90, color: '#1572b6' },
        { name: 'JavaScript', level: 80, color: '#f7df1e' },
        { name: 'Vue.js', level: 70, color: '#4fc08d' },
        { name: 'Tailwind CSS', level: 85, color: '#06b6d4' }
      ],
      backendSkills: [
        { name: 'Node.js', level: 80, color: '#339933' },
        { name: 'PHP', level: 90, color: '#777bb4' },
        { name: 'Python', level: 70, color: '#3776ab' },
        { name: 'MySQL', level: 95, color: '#4479a1' },
      ],
      toolsSkills: [
        { name: 'Git & GitHub', level: 90, color: '#f05032' },
        { name: 'VS Code', level: 95, color: '#007acc' },
        { name: 'Figma', level: 80, color: '#f24e1e' },
        { name: 'Terminal/CLI', level: 85, color: '#4d4d4d' },
        { name: 'Responsive Design', level: 90, color: '#ff6b6b' }
      ],
      technologies: [
        { name: 'HTML5', icon: '🌐', color: '#e34f26' },
        { name: 'CSS3', icon: '🎨', color: '#1572b6' },
        { name: 'JavaScript', icon: '⚡', color: '#f7df1e' },
        { name: 'Vue.js', icon: '💚', color: '#4fc08d' },
        { name: 'Node.js', icon: '🟢', color: '#339933' },
        { name: 'PHP', icon: '🐘', color: '#777bb4' },
        { name: 'Python', icon: '🐍', color: '#3776ab' },
        { name: 'MySQL', icon: '🗄️', color: '#4479a1' },
        { name: 'Git', icon: '📝', color: '#f05032' },
        { name: 'Figma', icon: '🎯', color: '#f24e1e' },
        { name: 'VS Code', icon: '💻', color: '#007acc' }
      ]
    }
  }
}
</script>

<style scoped>
.skills {
  padding: 5rem 0;
  background: #0d1117;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.section-header {
  text-align: center;
  margin-bottom: 4rem;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 700;
  color: #ffffff;
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.1rem;
  color: #8b949e;
  max-width: 600px;
  margin: 0 auto;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 3rem;
  margin-bottom: 4rem;
}

.skill-category {
  background: #161b22;
  padding: 2rem;
  border-radius: 15px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease;
  border: 1px solid #21262d;
}

.skill-category:hover {
  transform: translateY(-5px);
}

.category-title {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1.4rem;
  color: #ffffff;
  margin-bottom: 1.5rem;
  font-weight: 600;
}

.category-icon {
  font-size: 1.5rem;
}

.skills-list {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.skill-item {
  background: #21262d;
  padding: 1rem;
  border-radius: 10px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
  border: 1px solid #30363d;
}

.skill-info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 0.5rem;
}

.skill-name {
  font-weight: 600;
  color: #ffffff;
}

.skill-percentage {
  font-size: 0.9rem;
  color: #8b949e;
  font-weight: 500;
}

.skill-bar {
  width: 100%;
  height: 8px;
  background: #30363d;
  border-radius: 4px;
  overflow: hidden;
}

.skill-progress {
  height: 100%;
  border-radius: 4px;
  transition: width 1s ease-in-out;
  position: relative;
}

.skill-progress::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% { transform: translateX(-100%); }
  100% { transform: translateX(100%); }
}

.tech-showcase {
  text-align: center;
}

.tech-showcase h3 {
  font-size: 1.8rem;
  color: #ffffff;
  margin-bottom: 2rem;
  font-weight: 600;
}

.tech-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  gap: 1.5rem;
  max-width: 800px;
  margin: 0 auto;
}

.tech-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
  padding: 1rem;
  background: #161b22;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease;
  border: 1px solid #21262d;
}

.tech-item:hover {
  transform: translateY(-5px);
}

.tech-icon {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  color: white;
  margin-bottom: 0.5rem;
}

.tech-name {
  font-size: 0.9rem;
  font-weight: 500;
  color: #ffffff;
}

/* Mobile responsive */
@media screen and (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .skill-category {
    padding: 1.5rem;
  }

  .tech-grid {
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    gap: 1rem;
  }

  .tech-item {
    padding: 0.8rem;
  }

  .tech-icon {
    width: 40px;
    height: 40px;
    font-size: 1.2rem;
  }

  .section-title {
    font-size: 2rem;
  }
}

@media screen and (max-width: 480px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }

  .tech-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
</style> 