<template>
  <div class="portfolio-page">
    <section class="portfolio-hero">
      <div class="hero-background">
        <div class="gradient-overlay"></div>
        <div class="animated-shapes">
          <div class="shape shape-1"></div>
          <div class="shape shape-2"></div>
          <div class="shape shape-3"></div>
        </div>
      </div>
      <div class="container">
        <div class="row">
          <div class="col-12 text-center fade-in-up">
            <h1 class="hero-title">Nosso Portfólio</h1>
            <p class="hero-subtitle">Conheça alguns dos projetos que transformamos em realidade</p>
          </div>
        </div>
      </div>
    </section>

    <section class="partners-carousel">
      <div class="carousel-track">
        <div class="carousel-content">
          <div v-for="i in 3" :key="i" class="logos-wrapper">
            <div class="partner-logo"><i class="bi bi-cpu"></i></div>
            <div class="partner-logo"><i class="bi bi-heart-pulse"></i></div>
            <div class="partner-logo"><i class="bi bi-bar-chart"></i></div>
            <div class="partner-logo"><i class="bi bi-cart3"></i></div>
            <div class="partner-logo"><i class="bi bi-book"></i></div>
            <div class="partner-logo"><i class="bi bi-hospital"></i></div>
            <div class="partner-logo"><i class="bi bi-currency-dollar"></i></div>
            <div class="partner-logo"><i class="bi bi-graph-up-arrow"></i></div>
            <div class="partner-logo"><i class="bi bi-cup-hot"></i></div>
            <div class="partner-logo"><i class="bi bi-bag"></i></div>
          </div>
        </div>
      </div>
    </section>

    <section class="clients-section py-5">
      <div class="container">
        <div class="row mb-5">
          <div class="col-12 text-center">
            <h2 class="section-title">Principais Clientes</h2>
            <p class="section-subtitle">Trabalhamos com marcas de diversos segmentos, entregando soluções digitais inovadoras</p>
          </div>
        </div>
        <div class="row g-4">
          <div class="col-md-6 col-lg-4">
            <div class="client-card">
              <div class="client-icon">
                <i class="bi bi-hospital"></i>
              </div>
              <h4>Uniodonto Porto Alegre</h4>
              <p>Saúde e Odontologia</p>
              <span class="client-desc">Desenvolvimento de plataforma SaaS para gestão de horários e consultas odontológicas, facilitando o agendamento e atendimento.</span>
            </div>
          </div>
          <div class="col-md-6 col-lg-4">
            <div class="client-card">
              <div class="client-icon">
                <i class="bi bi-fuel-pump"></i>
              </div>
              <h4>Posto Barão</h4>
              <p>Combustíveis e Conveniência</p>
              <span class="client-desc">Website institucional apresentando os serviços da rede de postos, promovendo visão moderna e acessível.</span>
            </div>
          </div>
          <div class="col-md-6 col-lg-4">
            <div class="client-card">
              <div class="client-icon">
                <i class="bi bi-gear"></i>
              </div>
              <h4>Metalúrgica Guimaza</h4>
              <p>Indústria Metalúrgica</p>
              <span class="client-desc">Site corporativo destacando produtos e serviços, reforçando a presença digital da empresa no mercado industrial.</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="portfolio-grid py-5">
      <div class="container">
        <div class="row g-4">
          <div 
            v-for="(project, index) in projects" 
            :key="index"
            class="col-md-6 col-lg-4"
          >
            <div class="portfolio-card" :style="{ animationDelay: `${index * 0.1}s` }">
              <div class="portfolio-image">
                <div class="image-overlay">
                  <div class="overlay-content">
                    <h3>{{ project.title }}</h3>
                    <p>{{ project.category }}</p>
                    <span class="client-name">Cliente: {{ project.client }}</span>
                  </div>
                </div>
                <img :src="project.image" :alt="project.title" class="card-image" />
                <div class="image-title">
                  <h4>{{ project.title }}</h4>
                </div>
              </div>
              <div class="portfolio-info">
                <p class="client-label">{{ project.client }}</p>
                <p>{{ project.description }}</p>
                <a :href="project.link" class="btn-view-project">
                  Ver Projeto
                  <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
                    <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

interface Project {
  title: string
  category: string
  client: string
  description: string
  image: string
  link: string
}

const projects: Project[] = [
  {
    title: 'Quero Agenda',
    category: 'SaaS Platform',
    client: 'Uniodonto Porto Alegre',
    description: 'SaaS para gerenciamento de horarios e consultas odontológicas.',
    image: 'https://images.unsplash.com/photo-1629909613654-28e377c37b09?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Rede de posto Barão',
    category: 'Website',
    client: 'Posto Barão',
    description: 'Website institucional para o Posto Barão.',
    image: 'https://images.unsplash.com/photo-1545262810-77515befe149?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Metalúrgica Guimaza',
    category: 'Website',
    client: 'Guimaza',
    description: 'Website institucional para a Metalúrgica Guimaza.',
    image: 'https://images.unsplash.com/photo-1565008576549-57569a49371d?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Dashboard Analytics',
    category: 'Web App',
    client: 'DataViz Pro',
    description: 'Painel administrativo com visualização de dados em tempo real.',
    image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Marketplace',
    category: 'Platform',
    client: 'BuyHub Marketplace',
    description: 'Plataforma de marketplace multi-vendedores.',
    image: 'https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'SaaS Platform',
    category: 'Web App',
    client: 'ProjectHub Inc',
    description: 'Plataforma SaaS para gestão de projetos.',
    image: 'https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'E-commerce Gourmet',
    category: 'E-commerce',
    client: 'Sabores Premium',
    description: 'Loja online de produtos gourmet com sistema de assinatura.',
    image: 'https://images.unsplash.com/photo-1556910103-1c02745aae4d?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Portal Educacional',
    category: 'Platform',
    client: 'EduTech Online',
    description: 'Plataforma de cursos online com videoconferência.',
    image: 'https://images.unsplash.com/photo-1501504905252-473c47e087f8?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'App Delivery',
    category: 'Mobile App',
    client: 'QuickFood Delivery',
    description: 'Aplicativo de delivery com rastreamento em tempo real.',
    image: 'https://images.unsplash.com/photo-1526367790999-0150786686a2?w=800&h=600&fit=crop',
    link: '#'
  }
]
</script>

<style scoped>
.portfolio-page {
  min-height: 100vh;
}

.portfolio-hero {
  position: relative;
  overflow: hidden;
  padding: 150px 0 100px;
  margin-top: 80px;
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
  font-size: 4rem;
  font-weight: 800;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 1rem;
}

.hero-subtitle {
  font-size: 1.3rem;
  color: rgba(255, 255, 255, 0.8);
}

.clients-section {
  background: white;
  padding: 80px 0;
}

.section-title {
  font-size: 2.5rem;
  font-weight: 800;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.1rem;
  color: #64748b;
  max-width: 700px;
  margin: 0 auto;
}

.client-card {
  background: white;
  border: 2px solid #e2e8f0;
  border-radius: 20px;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.client-card:hover {
  transform: translateY(-5px);
  border-color: #6366f1;
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.15);
}

.client-icon {
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
}

.client-icon i {
  font-size: 2.5rem;
  color: white;
}

.client-card h4 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 0.5rem;
}

.client-card p {
  font-size: 0.9rem;
  color: #6366f1;
  font-weight: 600;
  margin-bottom: 1rem;
}

.client-desc {
  font-size: 0.95rem;
  color: #64748b;
  line-height: 1.6;
}

.portfolio-grid {
  background: #f8fafc;
  padding: 80px 0;
}

.portfolio-card {
  background: white;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  transition: all 0.4s ease;
  animation: fadeInUp 0.8s ease-out;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.portfolio-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}

.portfolio-image {
  position: relative;
  overflow: hidden;
  height: 250px;
}

.card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.portfolio-card:hover .card-image {
  transform: scale(1.1);
}

.image-title {
  position: absolute;
  bottom: 15px;
  right: 15px;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  padding: 0.7rem 1.3rem;
  border-radius: 12px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.3);
  transition: all 0.3s ease;
}

.portfolio-card:hover .image-title {
  transform: translateY(-3px);
  box-shadow: 0 12px 40px rgba(99, 102, 241, 0.3);
}

.image-title h4 {
  font-size: 1rem;
  font-weight: 800;
  letter-spacing: 0.5px;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin: 0;
  text-transform: uppercase;
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(99, 102, 241, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.4s ease;
}

.portfolio-card:hover .image-overlay {
  opacity: 1;
}

.overlay-content {
  text-align: center;
  color: white;
  padding: 2rem;
}

.overlay-content h3 {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
}

.overlay-content p {
  margin-bottom: 0.5rem;
  opacity: 0.9;
}

.client-name {
  font-size: 0.9rem;
  opacity: 0.8;
}

.portfolio-info {
  padding: 1.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.client-label {
  font-size: 0.85rem;
  color: #6366f1;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.portfolio-info p {
  color: #64748b;
  margin-bottom: 1rem;
  flex: 1;
  min-height: 3rem;
}

.partners-carousel {
  background: white;
  padding: 25px 0;
  overflow: hidden;
  border-top: 1px solid #e2e8f0;
  border-bottom: 1px solid #e2e8f0;
}

.carousel-track {
  width: 100%;
  overflow: hidden;
}

.carousel-content {
  display: flex;
  animation: scroll 30s linear infinite;
}

.logos-wrapper {
  display: flex;
  align-items: center;
  gap: 4rem;
  flex-shrink: 0;
}

.partner-logo {
  font-size: 2.5rem;
  font-weight: 700;
  color: #64748b;
  white-space: nowrap;
  opacity: 0.7;
  transition: opacity 0.3s ease;
  display: flex;
  align-items: center;
  justify-content: center;
}

.partner-logo:hover {
  opacity: 1;
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-33.33%);
  }
}

.btn-view-project {
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  color: white;
  padding: 0.4rem 0.9rem;
  border-radius: 18px;
  text-decoration: none;
  font-weight: 600;
  font-size: 0.75rem;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  margin-top: auto;
  align-self: flex-start;
  white-space: nowrap;
}

.btn-view-project:hover {
  transform: translateX(5px);
  box-shadow: 0 5px 15px rgba(99, 102, 241, 0.4);
  color: white;
}

.btn-view-project svg {
  transition: transform 0.3s ease;
}

.btn-view-project:hover svg {
  transform: translateX(3px);
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2.5rem;
  }
}

@keyframes float {
  0%, 100% {
    transform: translateY(0) rotate(0deg);
  }
  25% {
    transform: translateY(-20px) rotate(5deg);
  }
  50% {
    transform: translateY(-10px) rotate(-5deg);
  }
  75% {
    transform: translateY(-30px) rotate(3deg);
  }
}
</style>
