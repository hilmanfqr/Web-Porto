<template>
  <div id="app">
    <HeaderNav />
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ProjectsSection />
    <ContactSection />
    <FooterSection />
  </div>
</template>

<script>
import HeaderNav from './components/Header.vue'
import HeroSection from './components/Hero.vue'
import AboutSection from './components/About.vue'
import SkillsSection from './components/Skills.vue'
import ProjectsSection from './components/Projects.vue'
import ContactSection from './components/Contact.vue'
import FooterSection from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    HeaderNav,
    HeroSection,
    AboutSection,
    SkillsSection,
    ProjectsSection,
    ContactSection,
    FooterSection
  },
  mounted() {
    // Smooth scrolling for anchor links
    this.initSmoothScrolling()
  },
  methods: {
    initSmoothScrolling() {
      document.addEventListener('click', (e) => {
        if (e.target.matches('a[href^="#"]')) {
          e.preventDefault()
          const targetId = e.target.getAttribute('href')
          const targetElement = document.querySelector(targetId)
          
          if (targetElement) {
            targetElement.scrollIntoView({
              behavior: 'smooth',
              block: 'start'
            })
          }
        }
      })
    }
  }
}
</script>

<style>
/* Global styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  line-height: 1.6;
  color: #c9d1d9;
  background: #0d1117;
  overflow-x: hidden;
}

#app {
  min-height: 100vh;
}

/* Utility classes */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #161b22;
}

::-webkit-scrollbar-thumb {
  background: linear-gradient(135deg, #64ffda 0%, #00bcd4 100%);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(135deg, #4fd8b4 0%, #00a5b8 100%);
}

/* Selection color */
::selection {
  background: #64ffda;
  color: #0d1117;
}

::-moz-selection {
  background: #64ffda;
  color: #0d1117;
}

/* Animations */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slideInLeft {
  from {
    opacity: 0;
    transform: translateX(-50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes slideInRight {
  from {
    opacity: 0;
    transform: translateX(50px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

/* Loading animation */
@keyframes pulse {
  0%, 100% {
    opacity: 1;
  }
  50% {
    opacity: 0.5;
  }
}

/* Responsive font sizes */
@media screen and (max-width: 768px) {
  body {
    font-size: 14px;
  }
}

@media screen and (max-width: 480px) {
  body {
    font-size: 13px;
  }
}
</style>
