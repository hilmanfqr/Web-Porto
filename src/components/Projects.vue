<template>
  <section id="projects" class="projects">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">My Portfolio</h2>
        <p class="section-subtitle">Some projects I've worked on with various technologies</p>
      </div>

      <div class="projects-grid">
        <div class="project-card" v-for="project in projects" :key="project.id">
          <div class="project-image">
            <div class="image-placeholder" :style="{ background: project.gradient }">
              <img 
                :src="project.thumbnail" 
                :alt="project.title + ' thumbnail'"
                class="project-thumbnail"
                @error="handleImageError"
              />
            </div>
            <div class="project-overlay">
              <div class="project-links">
                <a :href="project.demo" class="project-link" target="_blank" rel="noopener">
                  <span>👁️</span> Demo
                </a>
                <a :href="project.github" class="project-link" target="_blank" rel="noopener">
                  <span>📝</span> Code
                </a>
              </div>
            </div>
          </div>
          
          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>
            
            <div class="project-tech">
              <span 
                class="tech-tag" 
                v-for="tech in project.technologies" 
                :key="tech"
              >
                {{ tech }}
              </span>
            </div>
            
            <div class="project-status">
              <span class="status-badge" :class="project.status">
                {{ getStatusText(project.status) }}
              </span>
            </div>
          </div>
        </div>
      </div>

      <div class="projects-cta">
        <h3>Interested in my work?</h3>
        <p>Let's discuss how I can help with your project</p>
        <a href="#contact" class="btn btn-primary">Contact Me</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ProjectsSection',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'E-Commerce Website',
          description: 'E-commerce platform with complete features like shopping cart, payment gateway, and admin dashboard.',
          technologies: ['PHP', 'CI3', 'MySQL', 'Bootstrap', 'JavaScript'],
          demo: 'https://kitatoko.lovestoblog.com/home',
          github: '#',
          status: 'completed',
          thumbnail: require('@/assets/thumbnails/tokokita.png'),
          gradient: 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)'
        },
        {
          id: 2,
          title: 'Task Management App',
          description: 'Task management application with real-time collaboration, drag & drop, and notification features.',
          technologies: ['React', 'Express.js', 'MongoDB', 'Socket.io'],
          demo: '#',
          github: '#',
          status: 'planning',
          thumbnail: 'https://via.placeholder.com/400x300/f093fb/ffffff?text=Task+Management',
          gradient: 'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)'
        },
        {
          id: 3,
          title: 'CMS Website',
          description: 'Content Management System for a website with a modern design, smooth animations, and fully responsive layout.',
          technologies: ['PHP', 'Laravel', 'MySQL', 'Bootstrap', 'JavaScript'],
          demo: '#',
          github: 'https://github.com/hilmanfqr/CMSWEB',
          status: 'completed',
          thumbnail: require('@/assets/thumbnails/cms.png'),
          gradient: 'linear-gradient(135deg, #4facfe 0%, #00f2fe 100%)'
        },
        {
          id: 4,
          title: 'Portfolio Website',
          description: 'Personal portfolio website with modern design, smooth animations, and fully responsive layout.',
          technologies: ['Vue.js', 'CSS3', 'JavaScript', 'Responsive'],
          demo: '#',
          github: '#',
          status: 'in-progress',
          thumbnail: require('@/assets/thumbnails/porto.png'),
          gradient: 'linear-gradient(135deg, #fa709a 0%, #fee140 100%)'
        },
        {
          id: 5,
          title: 'Planning Budget',
          description: 'Website for personal use to manage and track my budget and expenses.',
          technologies: ['PHP', 'MySQL', 'Bootstrap', 'JavaScript'],
          demo: '#',
          github: 'https://github.com/hilmanfqr/perencanaan-budget',
          status: 'completed',
          thumbnail: require('@/assets/thumbnails/budget.png'),
          gradient: 'linear-gradient(135deg, #a8edea 0%, #fed6e3 100%)'
        },
        {
          id: 6,
          title: 'Learning Management System',
          description: 'Online learning system with video streaming, interactive quizzes, and progress tracking.',
          technologies: ['React', 'Node.js', 'PostgreSQL', 'Redis'],
          demo: '#',
          github: '#',
          status: 'planning',
          thumbnail: 'https://via.placeholder.com/400x300/ffecd2/000000?text=LMS+System',
          gradient: 'linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%)'
        }
      ]
    }
  },
  methods: {
    getStatusText(status) {
      const statusMap = {
        'completed': 'Completed',
        'in-progress': 'In Progress',
        'planning': 'Planning'
      }
      return statusMap[status] || status
    },
    handleImageError(event) {
      // If image fails to load, show a placeholder
      event.target.style.display = 'none'
      const placeholder = document.createElement('div')
      placeholder.className = 'image-fallback'
      placeholder.textContent = '🖼️'
      event.target.parentNode.appendChild(placeholder)
    }
  }
}
</script>

<style scoped>
.projects {
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

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.project-card {
  background: #21262d;
  border-radius: 15px;
  overflow: hidden;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid #30363d;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
}

.project-image {
  position: relative;
  height: 200px;
  overflow: hidden;
}

.image-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 4rem;
}

.project-thumbnail {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 10px;
  transition: transform 0.3s ease;
}

.project-card:hover .project-thumbnail {
  transform: scale(1.05);
}

.image-fallback {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
  font-size: 4rem;
  color: white;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-links {
  display: flex;
  gap: 1rem;
}

.project-link {
  padding: 0.8rem 1.5rem;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  text-decoration: none;
  border-radius: 25px;
  font-weight: 500;
  transition: background 0.3s ease;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.3);
}

.project-link:hover {
  background: rgba(255, 255, 255, 0.3);
}

.project-content {
  padding: 1.5rem;
}

.project-title {
  font-size: 1.4rem;
  font-weight: 600;
  color: #ffffff;
  margin-bottom: 1rem;
}

.project-description {
  color: #8b949e;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  font-size: 0.95rem;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1rem;
}

.tech-tag {
  background: rgba(100, 255, 218, 0.1);
  color: #64ffda;
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 500;
  border: 1px solid rgba(100, 255, 218, 0.2);
}

.project-status {
  display: flex;
  justify-content: flex-end;
}

.status-badge {
  padding: 0.4rem 1rem;
  border-radius: 20px;
  font-size: 0.8rem;
  font-weight: 500;
}

.status-badge.completed {
  background: #e8f5e8;
  color: #2e7d32;
}

.status-badge.in-progress {
  background: #fff3e0;
  color: #f57c00;
}

.status-badge.planning {
  background: #f3e5f5;
  color: #7b1fa2;
}

.projects-cta {
  text-align: center;
  background: #21262d;
  padding: 3rem;
  border-radius: 15px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.3);
  border: 1px solid #30363d;
}

.projects-cta h3 {
  font-size: 1.8rem;
  color: #ffffff;
  margin-bottom: 1rem;
}

.projects-cta p {
  color: #8b949e;
  margin-bottom: 2rem;
  font-size: 1.1rem;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  display: inline-block;
}

.btn-primary {
  background: linear-gradient(45deg, #64ffda, #00bcd4);
  color: #0d1117;
  font-weight: 700;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(100, 255, 218, 0.4);
}

/* Mobile responsive */
@media screen and (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }

  .project-card {
    margin: 0 auto;
    max-width: 400px;
  }

  .projects-cta {
    padding: 2rem;
  }

  .section-title {
    font-size: 2rem;
  }
}

@media screen and (max-width: 480px) {
  .project-links {
    flex-direction: column;
    gap: 0.5rem;
  }

  .project-link {
    padding: 0.6rem 1rem;
    font-size: 0.9rem;
  }

  .projects-cta h3 {
    font-size: 1.5rem;
  }
}
</style> 