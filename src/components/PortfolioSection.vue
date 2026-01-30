<template>
  <section id="portfolio" class="portfolio-section py-5">
    <div class="container">
      <div class="row mb-5">
        <div class="col-12 text-center fade-in-up">
          <h2 class="section-title">Portfólio</h2>
          <p class="section-subtitle">Alguns de nossos trabalhos recentes</p>
        </div>
      </div>

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
                  <a href="#" class="btn btn-light btn-sm">Ver Projeto</a>
                </div>
              </div>
              <img :src="project.image" :alt="project.title" class="card-image" />
              <div class="image-title">
                <h4>{{ project.title }}</h4>
              </div>
            </div>
            <div class="portfolio-info">
              <p>{{ project.description }}</p>
              <a :href="project.link" class="btn-view-project">
                Ver Projeto
                <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" fill="currentColor" viewBox="0 0 16 16">
                  <path fill-rule="evenodd" d="M1 8a.5.5 0 0 1 .5-.5h11.793l-3.147-3.146a.5.5 0 0 1 .708-.708l4 4a.5.5 0 0 1 0 .708l-4 4a.5.5 0 0 1-.708-.708L13.293 8.5H1.5A.5.5 0 0 1 1 8z"/>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
interface Project {
  title: string
  category: string
  description: string
  image: string
  link: string
}

const projects: Project[] = [
  {
    title: 'Loja Fashion',
    category: 'E-commerce',
    description: 'E-commerce completo com integração de pagamentos e gestão.',
    image: 'https://images.unsplash.com/photo-1441986300917-64674bd600d8?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'App Fitness',
    category: 'Mobile App',
    description: 'Aplicativo de treinos e acompanhamento nutricional.',
    image: 'https://images.unsplash.com/photo-1534438327276-14e5300c3a48?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Site Corporativo',
    category: 'Website',
    description: 'Website institucional com CMS personalizado.',
    image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Dashboard Analytics',
    category: 'Web App',
    description: 'Painel administrativo com visualização de dados em tempo real.',
    image: 'https://images.unsplash.com/photo-1551288049-bebda4e38f71?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'Marketplace',
    category: 'Platform',
    description: 'Plataforma de marketplace multi-vendedores.',
    image: 'https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=800&h=600&fit=crop',
    link: '#'
  },
  {
    title: 'SaaS Platform',
    category: 'Web App',
    description: 'Plataforma SaaS para gestão de projetos.',
    image: 'https://images.unsplash.com/photo-1454165804606-c3d57bc86b40?w=800&h=600&fit=crop',
    link: '#'
  }
]
</script>

<style scoped>
.portfolio-section {
  background: #f8fafc;
  padding: 100px 0;
}

.section-title {
  font-size: 3rem;
  font-weight: 800;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 1rem;
}

.section-subtitle {
  font-size: 1.2rem;
  color: #64748b;
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
  margin-bottom: 1rem;
  opacity: 0.9;
}

.portfolio-info {
  padding: 1.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.portfolio-info p {
  color: #64748b;
  margin-bottom: 1rem;
  flex: 1;
  min-height: 3rem;
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
</style>
