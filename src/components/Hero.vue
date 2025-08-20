<template>
  <section id="home" class="hero">
    <div class="hero-container">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">
            Hi, I'm <span class="highlight">Hilman</span>
          </h1>
          <h2 class="hero-subtitle">Web Developer & Fullstack Engineer</h2>
          <p class="hero-description">
            I'm a passionate developer who loves creating engaging and functional web and apps experiences. 
            Let's collaborate to bring your digital ideas to life!
          </p>
          <div class="hero-buttons">
            <a href="#projects" class="btn btn-primary">View Portfolio</a>
            <a href="#contact" class="btn btn-secondary">Contact Me</a>
          </div>
        </div>
        <div class="hero-image">
          <div class="image-placeholder">
            <!-- Using your local profile photo -->
            <img 
              src="@/assets/profile.jpg" 
              alt="Hilman Profile" 
              class="profile-image"
              @error="handleImageError"
              ref="profileImage"
            />
            
            <!-- Option 3: Keep the letter avatar as fallback -->
            <div class="avatar-fallback">
              <span>H</span>
            </div>
          </div>
        </div>
      </div>
      <div class="scroll-indicator">
        <div class="scroll-arrow"></div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
  methods: {
    handleImageError() {
      // Hide the image and show fallback avatar if image fails to load
      if (this.$refs.profileImage) {
        this.$refs.profileImage.style.display = 'none'
        const fallback = this.$refs.profileImage.nextElementSibling
        if (fallback) {
          fallback.style.display = 'flex'
        }
      }
    }
  }
}
</script>

<style scoped>
.hero {
  min-height: 100vh;
  background: linear-gradient(135deg, #0d1117 0%, #1a1a1a 50%, #161b22 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="white" opacity="0.1"/><circle cx="75" cy="75" r="1" fill="white" opacity="0.1"/><circle cx="50" cy="10" r="0.5" fill="white" opacity="0.1"/><circle cx="10" cy="60" r="0.5" fill="white" opacity="0.1"/><circle cx="90" cy="40" r="0.5" fill="white" opacity="0.1"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
  pointer-events: none;
}

.hero-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  width: 100%;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
  min-height: 80vh;
}

.hero-text {
  color: white;
  z-index: 2;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.highlight {
  background: linear-gradient(45deg, #64ffda, #00bcd4);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-subtitle {
  font-size: 1.5rem;
  font-weight: 300;
  margin-bottom: 1.5rem;
  opacity: 0.9;
}

.hero-description {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 2.5rem;
  opacity: 0.8;
  max-width: 500px;
}

.hero-buttons {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.btn {
  padding: 1rem 2rem;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  display: inline-block;
  border: 2px solid transparent;
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

.btn-secondary {
  background: transparent;
  color: white;
  border: 2px solid white;
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.1);
  color: #64ffda;
  transform: translateY(-2px);
}

.hero-image {
  display: flex;
  justify-content: center;
  align-items: center;
}

.image-placeholder {
  position: relative;
  z-index: 2;
}

.profile-image {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  object-fit: cover;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
  animation: float 6s ease-in-out infinite;
  border: 4px solid #64ffda;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.profile-image:hover {
  transform: scale(1.05);
  box-shadow: 0 25px 50px rgba(100, 255, 218, 0.3);
}

.avatar-fallback {
  width: 300px;
  height: 300px;
  border-radius: 50%;
  background: linear-gradient(45deg, #64ffda, #00bcd4);
  display: none; /* Hidden by default, show only if image fails to load */
  align-items: center;
  justify-content: center;
  font-size: 8rem;
  font-weight: bold;
  color: #0d1117;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
  animation: float 6s ease-in-out infinite;
  border: 3px solid rgba(100, 255, 218, 0.3);
}

@keyframes float {
  0%, 100% {
    transform: translateY(0px);
  }
  50% {
    transform: translateY(-20px);
  }
}

.scroll-indicator {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
}

.scroll-arrow {
  width: 2px;
  height: 30px;
  background: white;
  position: relative;
  animation: scroll 2s infinite;
}

.scroll-arrow::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: -4px;
  width: 10px;
  height: 10px;
  border-right: 2px solid white;
  border-bottom: 2px solid white;
  transform: rotate(45deg);
}

@keyframes scroll {
  0%, 100% {
    opacity: 0.4;
  }
  50% {
    opacity: 1;
  }
}

/* Mobile responsive */
@media screen and (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
    padding-top: 2rem;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-subtitle {
    font-size: 1.2rem;
  }

  .hero-description {
    font-size: 1rem;
    max-width: 100%;
  }

  .profile-image,
  .avatar-fallback {
    width: 200px;
    height: 200px;
  }
  
  .avatar-fallback {
    font-size: 5rem;
  }

  .hero-buttons {
    justify-content: center;
  }

  .btn {
    padding: 0.8rem 1.5rem;
    font-size: 0.9rem;
  }
}

@media screen and (max-width: 480px) {
  .hero-title {
    font-size: 2rem;
  }

  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }

  .btn {
    width: 200px;
    text-align: center;
  }
}
</style> 