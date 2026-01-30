<template>
  <section id="about" class="about-section py-5">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6 mb-4 mb-lg-0 fade-in-left">
          <div class="about-image">
            <div class="image-wrapper">
              <svg viewBox="0 0 500 400" xmlns="http://www.w3.org/2000/svg">
                <defs>
                  <linearGradient id="aboutGrad" x1="0%" y1="0%" x2="100%" y2="100%">
                    <stop offset="0%" style="stop-color:#6366f1;stop-opacity:1" />
                    <stop offset="100%" style="stop-color:#8b5cf6;stop-opacity:1" />
                  </linearGradient>
                </defs>
                <rect width="500" height="400" fill="url(#aboutGrad)" opacity="0.1" rx="20"/>
                <circle cx="150" cy="100" r="60" fill="url(#aboutGrad)" opacity="0.3"/>
                <circle cx="350" cy="120" r="40" fill="url(#aboutGrad)" opacity="0.3"/>
                <rect x="100" y="200" width="300" height="150" fill="url(#aboutGrad)" opacity="0.3" rx="15"/>
                <circle cx="250" cy="275" r="80" fill="#6366f1" opacity="0.2"/>
                <rect x="200" y="80" width="100" height="100" fill="#8b5cf6" opacity="0.2" rx="10"/>
              </svg>
            </div>
          </div>
        </div>
        <div class="col-lg-6 fade-in-right">
          <h2 class="section-title mb-4">Sobre a Dudis</h2>
          <p class="about-text">
            Somos uma agência digital apaixonada por transformar ideias em experiências 
            digitais marcantes. Com mais de 5 anos de experiência, ajudamos empresas de 
            todos os tamanhos a crescerem no mundo digital.
          </p>
          <p class="about-text">
            Nossa equipe é formada por profissionais especializados em desenvolvimento web, 
            design, marketing digital e estratégia. Acreditamos que cada projeto é único e 
            merece uma solução personalizada.
          </p>

          <div class="about-features mt-4">
            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 16 16">
                  <path d="M10.97 4.97a.75.75 0 0 1 1.07 1.05l-3.99 4.99a.75.75 0 0 1-1.08.02L4.324 8.384a.75.75 0 1 1 1.06-1.06l2.094 2.093 3.473-4.425a.267.267 0 0 1 .02-.022z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h4>Experiência</h4>
                <p>Mais de 150 projetos entregues com sucesso</p>
              </div>
            </div>

            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 16 16">
                  <path d="M10.97 4.97a.75.75 0 0 1 1.07 1.05l-3.99 4.99a.75.75 0 0 1-1.08.02L4.324 8.384a.75.75 0 1 1 1.06-1.06l2.094 2.093 3.473-4.425a.267.267 0 0 1 .02-.022z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h4>Qualidade</h4>
                <p>Código limpo e otimizado seguindo as melhores práticas</p>
              </div>
            </div>

            <div class="feature-item">
              <div class="feature-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="currentColor" viewBox="0 0 16 16">
                  <path d="M10.97 4.97a.75.75 0 0 1 1.07 1.05l-3.99 4.99a.75.75 0 0 1-1.08.02L4.324 8.384a.75.75 0 1 1 1.06-1.06l2.094 2.093 3.473-4.425a.267.267 0 0 1 .02-.022z"/>
                </svg>
              </div>
              <div class="feature-content">
                <h4>Suporte</h4>
                <p>Acompanhamento completo antes, durante e após o projeto</p>
              </div>
            </div>
          </div>

          <div class="mt-4">
            <a href="#contact" class="btn btn-primary btn-lg">Entre em Contato</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-section {
  background: linear-gradient(180deg, #1e293b 0%, #0f172a 100%);
  padding: 100px 0;
  color: white;
}

.section-title {
  font-size: 3rem;
  font-weight: 800;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.about-text {
  font-size: 1.1rem;
  color: rgba(255, 255, 255, 0.8);
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.about-image {
  position: relative;
}

.image-wrapper {
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
  animation: float 6s ease-in-out infinite;
}

.image-wrapper svg {
  width: 100%;
  height: auto;
}

@keyframes float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
}

.about-features {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.feature-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
}

.feature-icon {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  color: white;
}

.feature-content h4 {
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 0.3rem;
  color: white;
}

.feature-content p {
  color: rgba(255, 255, 255, 0.7);
  margin: 0;
  font-size: 0.95rem;
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
</style>
