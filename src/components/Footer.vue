<template>
  <footer class="footer">
    <div class="container">
      <div class="footer-content">
        <div class="footer-info">
          <h3>Hilman</h3>
          <p>Passionate Web Developer & Designer who loves creating engaging digital experiences.</p>
        </div>
        
        <div class="footer-links">
          <h4>Quick Links</h4>
          <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
          </ul>
        </div>
        
        <div class="footer-social">
          <h4>Follow Me</h4>
          <div class="social-links">
            <a href="#" class="social-link">🐙</a>
            <a href="#" class="social-link">💼</a>
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p>&copy; {{ currentYear }} Hilman. Made with ❤️ using Vue.js</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'FooterSection',
  computed: {
    currentYear() {
      return new Date().getFullYear()
    }
  }
}
</script>

<style scoped>
.footer {
  background: #0d1117;
  color: white;
  padding: 3rem 0 1rem;
  border-top: 1px solid #21262d;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.footer-content {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr;
  gap: 3rem;
  margin-bottom: 2rem;
}

.footer-info h3 {
  font-size: 1.8rem;
  margin-bottom: 1rem;
  color: #64ffda;
}

.footer-info p {
  line-height: 1.6;
  opacity: 0.8;
}

.footer-links h4,
.footer-social h4 {
  font-size: 1.2rem;
  margin-bottom: 1rem;
  color: #64ffda;
}

.footer-links ul {
  list-style: none;
}

.footer-links li {
  margin-bottom: 0.5rem;
}

.footer-links a {
  color: white;
  text-decoration: none;
  opacity: 0.8;
  transition: opacity 0.3s ease;
}

.footer-links a:hover {
  opacity: 1;
  color: #64ffda;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-link {
  width: 40px;
  height: 40px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  font-size: 1.2rem;
  transition: background 0.3s ease, transform 0.3s ease;
  border: 1px solid rgba(100, 255, 218, 0.2);
}

.social-link:hover {
  background: #64ffda;
  color: #0d1117;
  transform: translateY(-2px);
}

.footer-bottom {
  text-align: center;
  padding-top: 2rem;
  border-top: 1px solid rgba(100, 255, 218, 0.1);
}

.footer-bottom p {
  opacity: 0.7;
  font-size: 0.9rem;
}

/* Mobile responsive */
@media screen and (max-width: 768px) {
  .footer-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }

  .social-links {
    justify-content: center;
  }
}
</style> 