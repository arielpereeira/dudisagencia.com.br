<template>
  <section id="home" class="hero-section">
    <div class="hero-background">
      <div class="gradient-overlay"></div>
      <div class="animated-shapes">
        <div class="shape shape-1"></div>
        <div class="shape shape-2"></div>
        <div class="shape shape-3"></div>
      </div>
    </div>
    
    <div class="container">
      <div class="row align-items-center min-vh-100">
        <div class="col-lg-6 fade-in-left">
          <h1 class="hero-title mb-4">
            Transforme sua
            <span class="gradient-text"> Presença Digital</span>
          </h1>
          <p class="hero-subtitle mb-4">
            Somos a Dudis, uma agência digital especializada em criar experiências 
            incríveis que conectam marcas e pessoas através da tecnologia.
          </p>
          <div class="hero-buttons">
            <a href="#contact" class="btn btn-primary btn-lg me-3">
              Fale Conosco
            </a>
            <a href="#portfolio" class="btn btn-outline-light btn-lg">
              Ver Projetos
            </a>
          </div>
          <div class="hero-stats mt-5">
            <div class="stat-item">
              <h3 class="stat-number">150+</h3>
              <p class="stat-label">Projetos</p>
            </div>
            <div class="stat-item">
              <h3 class="stat-number">95%</h3>
              <p class="stat-label">Satisfação</p>
            </div>
            <div class="stat-item">
              <h3 class="stat-number">5+</h3>
              <p class="stat-label">Anos</p>
            </div>
          </div>
        </div>
        <div class="col-lg-6 fade-in-right">
          <div class="hero-image float-animation">
            <div class="image-placeholder">
              <svg viewBox="0 0 500 500" xmlns="http://www.w3.org/2000/svg">
                <defs>
                  <linearGradient id="grad1" x1="0%" y1="0%" x2="100%" y2="100%">
                    <stop offset="0%" style="stop-color:#6366f1;stop-opacity:1" />
                    <stop offset="100%" style="stop-color:#8b5cf6;stop-opacity:1" />
                  </linearGradient>
                </defs>
                <rect width="500" height="500" fill="url(#grad1)" opacity="0.1" rx="20"/>
                <circle cx="250" cy="200" r="80" fill="url(#grad1)" opacity="0.3"/>
                <rect x="150" y="300" width="200" height="120" fill="url(#grad1)" opacity="0.3" rx="10"/>
                <circle cx="150" cy="150" r="30" fill="#6366f1" opacity="0.5"/>
                <circle cx="350" cy="350" r="40" fill="#8b5cf6" opacity="0.5"/>
              </svg>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero-section {
  position: relative;
  overflow: hidden;
  min-height: 100vh;
  display: flex;
  align-items: center;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
  z-index: -1;
}

.gradient-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 20% 50%, rgba(99, 102, 241, 0.15) 0%, transparent 50%),
              radial-gradient(circle at 80% 80%, rgba(139, 92, 246, 0.15) 0%, transparent 50%);
}

.animated-shapes {
  position: absolute;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.shape {
  position: absolute;
  border-radius: 50%;
  filter: blur(60px);
  opacity: 0.3;
  animation: float 8s ease-in-out infinite;
}

.shape-1 {
  width: 300px;
  height: 300px;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  top: 10%;
  left: 10%;
  animation-delay: 0s;
}

.shape-2 {
  width: 400px;
  height: 400px;
  background: linear-gradient(135deg, #8b5cf6, #f59e0b);
  bottom: 10%;
  right: 10%;
  animation-delay: 2s;
}

.shape-3 {
  width: 200px;
  height: 200px;
  background: linear-gradient(135deg, #f59e0b, #6366f1);
  top: 50%;
  left: 50%;
  animation-delay: 4s;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  color: white;
  line-height: 1.2;
}

.gradient-text {
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 50%, #f59e0b 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-size: 200% auto;
  animation: gradient-animation 3s linear infinite;
}

@keyframes gradient-animation {
  0% {
    background-position: 0% center;
  }
  100% {
    background-position: 200% center;
  }
}

.hero-subtitle {
  font-size: 1.2rem;
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.8;
}

.btn-primary {
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  border: none;
  padding: 1rem 2.5rem;
  border-radius: 30px;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
}

.btn-outline-light {
  border: 2px solid rgba(255, 255, 255, 0.3);
  padding: 1rem 2.5rem;
  border-radius: 30px;
  font-weight: 600;
  color: white;
  transition: all 0.3s ease;
}

.btn-outline-light:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(255, 255, 255, 0.5);
  transform: translateY(-3px);
}

.hero-stats {
  display: flex;
  gap: 3rem;
}

.stat-item {
  text-align: center;
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 0.5rem;
}

.stat-label {
  color: rgba(255, 255, 255, 0.7);
  font-size: 0.9rem;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.hero-image {
  position: relative;
}

.image-placeholder {
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
}

.image-placeholder svg {
  width: 100%;
  height: auto;
}

@media (max-width: 991px) {
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-stats {
    gap: 2rem;
  }
  
  .stat-number {
    font-size: 2rem;
  }
}
</style>
