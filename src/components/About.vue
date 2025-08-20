<template>
  <section id="about" class="about">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">About Me</h2>
        <p class="section-subtitle">Get to know more about my journey and passion</p>
      </div>
      
      <div class="about-content">
        <div class="about-text">
          <h3>Hello! I'm Hilman</h3>
          <p>
            I'm a passionate Web Developer who loves creating engaging and functional digital experiences. 
            As a fresh graduate with experience in various modern technologies, I enjoy turning creative 
            ideas into real web solutions.
          </p>
          <p>
            My journey in programming started from a great curiosity about how websites work. 
            Over time, this passion has developed into skills in front-end and back-end development.
          </p>
          
          <div class="highlights">
            <div class="highlight-item">
              <h4>🎯 Focus</h4>
              <p>User Experience & Clean Code</p>
            </div>
            <div class="highlight-item">
              <h4>💡 Passion</h4>
              <p>Modern Web Technologies</p>
            </div>
            <div class="highlight-item">
              <h4>🚀 Goal</h4>
              <p>Continuous Learning & Innovation</p>
            </div>
          </div>
        </div>
        
        <div class="about-stats">
          <div class="stat-card">
            <div class="stat-number">Fresh</div>
            <div class="stat-label">Graduate</div>
          </div>
          <div class="stat-card">
            <div class="stat-number">5+</div>
            <div class="stat-label">Projects Completed</div>
          </div>
          <div class="stat-card">
            <div class="stat-number">8+</div>
            <div class="stat-label">Technologies Learned</div>
          </div>
        </div>
      </div>
      
      <div class="journey">
        <h3>My Journey</h3>
        <div class="timeline">
          <div class="timeline-item">
            <div class="timeline-dot"></div>
            <div class="timeline-content">
              <h4>2019 - Starting the Journey</h4>
              <p>Started learning and expolring HTML, CSS, JavaScript and Framework through college as a student</p>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot"></div>
            <div class="timeline-content">
              <h4>2023 - Internship</h4>
              <p>Learned Laravel Framework as a Fullstack Developer</p>
            </div>
          </div>
          <div class="timeline-item">
            <div class="timeline-dot"></div>
            <div class="timeline-content">
              <h4>2025 - Graduation</h4>
              <p>Completed my study and graduated, ready to start my career</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutSection'
}
</script>

<style scoped>
.about {
  padding: 5rem 0;
  background: #161b22;
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

.about-content {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 4rem;
  margin-bottom: 4rem;
  align-items: start;
}

.about-text h3 {
  font-size: 1.8rem;
  color: #ffffff;
  margin-bottom: 1.5rem;
}

.about-text p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: #c9d1d9;
  margin-bottom: 1.5rem;
}

.highlights {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.highlight-item {
  background: #21262d;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease;
  border: 1px solid #30363d;
}

.highlight-item:hover {
  transform: translateY(-5px);
}

.highlight-item h4 {
  font-size: 1.1rem;
  color: #64ffda;
  margin-bottom: 0.5rem;
}

.highlight-item p {
  font-size: 0.9rem;
  color: #8b949e;
  margin: 0;
}

.about-stats {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.stat-card {
  background: linear-gradient(135deg, #64ffda 0%, #00bcd4 100%);
  color: #0d1117;
  padding: 2rem;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 10px 25px rgba(100, 255, 218, 0.3);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 800;
  margin-bottom: 0.5rem;
}

.stat-label {
  font-size: 0.9rem;
  opacity: 0.9;
}

.journey {
  margin-top: 3rem;
}

.journey h3 {
  font-size: 1.8rem;
  color: #ffffff;
  margin-bottom: 2rem;
  text-align: center;
}

.timeline {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 50%;
  top: 0;
  bottom: 0;
  width: 2px;
  background: #64ffda;
  transform: translateX(-50%);
}

.timeline-item {
  position: relative;
  margin-bottom: 3rem;
  display: flex;
  align-items: center;
}

.timeline-item:nth-child(odd) {
  flex-direction: row;
}

.timeline-item:nth-child(even) {
  flex-direction: row-reverse;
}

.timeline-dot {
  width: 20px;
  height: 20px;
  background: #64ffda;
  border-radius: 50%;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
  border: 4px solid #161b22;
  box-shadow: 0 0 0 4px #64ffda;
}

.timeline-content {
  background: #21262d;
  padding: 1.5rem;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  width: 45%;
  position: relative;
  border: 1px solid #30363d;
}

.timeline-content h4 {
  color: #ffffff;
  margin-bottom: 0.5rem;
  font-size: 1.1rem;
}

.timeline-content p {
  color: #8b949e;
  margin: 0;
  font-size: 0.95rem;
}

/* Mobile responsive */
@media screen and (max-width: 768px) {
  .about-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .highlights {
    grid-template-columns: 1fr;
  }

  .about-stats {
    flex-direction: row;
    justify-content: space-between;
  }

  .stat-card {
    padding: 1.5rem 1rem;
  }

  .stat-number {
    font-size: 2rem;
  }

  .timeline::before {
    left: 20px;
  }

  .timeline-item {
    flex-direction: row !important;
    padding-left: 50px;
  }

  .timeline-dot {
    left: 20px;
  }

  .timeline-content {
    width: 100%;
  }

  .section-title {
    font-size: 2rem;
  }
}

@media screen and (max-width: 480px) {
  .about-stats {
    flex-direction: column;
  }

  .highlights {
    gap: 1rem;
  }

  .highlight-item {
    padding: 1rem;
  }
}
</style> 