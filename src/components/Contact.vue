<template>
  <section id="contact" class="contact">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Let's Collaborate</h2>
        <p class="section-subtitle">Have an interesting project? Let's discuss how I can help bring it to life</p>
      </div>

      <div class="contact-content">
        <div class="contact-info">
          <h3>Let's Connect</h3>
          <p>
            I'm always open to discussions about new projects, collaboration opportunities, 
            or just sharing about the latest web technologies.
          </p>

          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">📧</div>
              <div class="method-info">
                <h4>Email</h4>
                <p>hilmansfiqr@gmail.com</p>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">📍</div>
              <div class="method-info">
                <h4>Location</h4>
                <p>Jakarta, Indonesia</p>
              </div>
            </div>
          </div>

          <div class="social-links">
            <h4>Follow Me</h4>
            <div class="social-grid">
              <a href="https://github.com/hilmanfqr" class="social-link github">
                <span class="social-icon">🐙</span>
                <span>GitHub</span>
              </a>
              <a href="https://www.linkedin.com/in/hilmanfiqri/" class="social-link linkedin">
                <span class="social-icon">💼</span>
                <span>LinkedIn</span>
              </a>
            </div>
          </div>
        </div>

        <div class="contact-form-container">
          <form class="contact-form" @submit.prevent="submitForm">
            <h3>Send Message</h3>
            
            <div class="form-group">
              <label for="name">Full Name</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name" 
                required
                placeholder="Enter your name"
              />
            </div>

            <div class="form-group">
              <label for="email">Email</label>
              <input 
                type="email" 
                id="email" 
                v-model="form.email" 
                required
                placeholder="name@email.com"
              />
            </div>

            <div class="form-group">
              <label for="subject">Subject</label>
              <select id="subject" v-model="form.subject" required>
                <option value="">Select subject</option>
                <option value="project">Project Discussion</option>
                <option value="collaboration">Collaboration</option>
                <option value="job">Job Opportunity</option>
                <option value="other">Other</option>
              </select>
            </div>

            <div class="form-group">
              <label for="message">Message</label>
              <textarea 
                id="message" 
                v-model="form.message" 
                required
                rows="5"
                placeholder="Tell me about your project or idea..."
              ></textarea>
            </div>

            <button type="submit" class="submit-btn" :disabled="isSubmitting">
              <span v-if="!isSubmitting">Send Message</span>
              <span v-else>Sending...</span>
            </button>

            <div v-if="submitMessage" class="submit-message" :class="submitStatus">
              {{ submitMessage }}
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'ContactSection',
  data() {
    return {
      form: {
        name: '',
        email: '',
        subject: '',
        message: ''
      },
      isSubmitting: false,
      submitMessage: '',
      submitStatus: ''
    }
  },
  methods: {
    async submitForm() {
      this.isSubmitting = true
      this.submitMessage = ''
      
      try {
        // Simulasi pengiriman form
        await new Promise(resolve => setTimeout(resolve, 2000))
        
        // Reset form
        this.form = {
          name: '',
          email: '',
          subject: '',
          message: ''
        }
        
        this.submitMessage = 'Message sent successfully! I will respond soon.'
        this.submitStatus = 'success'
        
        // Clear message after 5 seconds
        setTimeout(() => {
          this.submitMessage = ''
        }, 5000)
        
      } catch (error) {
        this.submitMessage = 'An error occurred. Please try again.'
        this.submitStatus = 'error'
      } finally {
        this.isSubmitting = false
      }
    }
  }
}
</script>

<style scoped>
.contact {
  padding: 5rem 0;
  background: linear-gradient(135deg, #0d1117 0%, #1a1a1a 50%, #161b22 100%);
  color: white;
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
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.1rem;
  opacity: 0.9;
  max-width: 600px;
  margin: 0 auto;
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-info h3 {
  font-size: 1.8rem;
  margin-bottom: 1rem;
  font-weight: 600;
}

.contact-info > p {
  font-size: 1.1rem;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 2rem;
}

.contact-methods {
  margin-bottom: 3rem;
}

.contact-method {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.method-icon {
  font-size: 2rem;
  width: 50px;
  text-align: center;
}

.method-info h4 {
  margin: 0 0 0.5rem 0;
  font-size: 1.1rem;
}

.method-info p {
  margin: 0;
  opacity: 0.8;
}

.social-links h4 {
  margin-bottom: 1rem;
  font-size: 1.2rem;
}

.social-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
}

.social-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  padding: 0.8rem;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 10px;
  text-decoration: none;
  color: white;
  transition: background 0.3s ease, transform 0.3s ease;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.1);
}

.social-link:hover {
  background: rgba(100, 255, 218, 0.1);
  transform: translateY(-2px);
  border-color: rgba(100, 255, 218, 0.3);
}

.social-icon {
  font-size: 1.2rem;
}

.contact-form-container {
  background: rgba(255, 255, 255, 0.05);
  padding: 2rem;
  border-radius: 15px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(100, 255, 218, 0.2);
}

.contact-form h3 {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
  font-weight: 600;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: 500;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 0.8rem;
  border: 1px solid rgba(100, 255, 218, 0.2);
  border-radius: 8px;
  background: rgba(255, 255, 255, 0.05);
  color: white;
  font-size: 1rem;
  backdrop-filter: blur(10px);
  transition: border-color 0.3s ease;
}

.form-group input::placeholder,
.form-group textarea::placeholder {
  color: rgba(255, 255, 255, 0.7);
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #64ffda;
  box-shadow: 0 0 0 2px rgba(100, 255, 218, 0.2);
}

.form-group select option {
  background: #0d1117;
  color: white;
}

.submit-btn {
  width: 100%;
  padding: 1rem;
  background: linear-gradient(45deg, #64ffda, #00bcd4);
  color: #0d1117;
  border: none;
  border-radius: 8px;
  font-size: 1.1rem;
  font-weight: 700;
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.submit-btn:hover:not(:disabled) {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(100, 255, 218, 0.4);
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.submit-message {
  margin-top: 1rem;
  padding: 0.8rem;
  border-radius: 8px;
  text-align: center;
  font-weight: 500;
}

.submit-message.success {
  background: rgba(76, 175, 80, 0.2);
  border: 1px solid rgba(76, 175, 80, 0.5);
}

.submit-message.error {
  background: rgba(244, 67, 54, 0.2);
  border: 1px solid rgba(244, 67, 54, 0.5);
}

/* Mobile responsive */
@media screen and (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .social-grid {
    grid-template-columns: 1fr;
  }

  .contact-form-container {
    padding: 1.5rem;
  }

  .section-title {
    font-size: 2rem;
  }
}

@media screen and (max-width: 480px) {
  .contact-method {
    flex-direction: column;
    text-align: center;
  }

  .method-icon {
    width: auto;
  }

  .social-link {
    justify-content: center;
  }
}
</style> 