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
              <div class="placeholder-image" :style="{ background: project.color }">
                <span class="project-number">#{{ index + 1 }}</span>
              </div>
            </div>
            <div class="portfolio-info">
              <h4>{{ project.title }}</h4>
              <p>{{ project.description }}</p>
              <div class="portfolio-tags">
                <span v-for="(tag, i) in project.tags" :key="i" class="tag">{{ tag }}</span>
              </div>
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
  tags: string[]
  color: string
}

const projects: Project[] = [
  {
    title: 'Loja Fashion',
    category: 'E-commerce',
    description: 'E-commerce completo com integração de pagamentos e gestão.',
    tags: ['Vue.js', 'Node.js', 'Stripe'],
    color: 'linear-gradient(135deg, #667eea 0%, #764ba2 100%)'
  },
  {
    title: 'App Fitness',
    category: 'Mobile App',
    description: 'Aplicativo de treinos e acompanhamento nutricional.',
    tags: ['React Native', 'Firebase'],
    color: 'linear-gradient(135deg, #f093fb 0%, #f5576c 100%)'
  },
  {
    title: 'Site Corporativo',
    category: 'Website',
    description: 'Website institucional com CMS personalizado.',
    tags: ['WordPress', 'PHP', 'MySQL'],
    color: 'linear-gradient(135deg, #4facfe 0%, #00f2fe 100%)'
  },
  {
    title: 'Dashboard Analytics',
    category: 'Web App',
    description: 'Painel administrativo com visualização de dados em tempo real.',
    tags: ['React', 'D3.js', 'Node.js'],
    color: 'linear-gradient(135deg, #43e97b 0%, #38f9d7 100%)'
  },
  {
    title: 'Marketplace',
    category: 'Platform',
    description: 'Plataforma de marketplace multi-vendedores.',
    tags: ['Vue.js', 'Laravel', 'Redis'],
    color: 'linear-gradient(135deg, #fa709a 0%, #fee140 100%)'
  },
  {
    title: 'SaaS Platform',
    category: 'Web App',
    description: 'Plataforma SaaS para gestão de projetos.',
    tags: ['Angular', 'NestJS', 'PostgreSQL'],
    color: 'linear-gradient(135deg, #30cfd0 0%, #330867 100%)'
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

.placeholder-image {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.4s ease;
}

.portfolio-card:hover .placeholder-image {
  transform: scale(1.1);
}

.project-number {
  font-size: 4rem;
  font-weight: 800;
  color: rgba(255, 255, 255, 0.3);
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

.portfolio-info h4 {
  font-size: 1.3rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 0.5rem;
  min-height: 2.6rem;
  display: flex;
  align-items: center;
}

.portfolio-info p {
  color: #64748b;
  margin-bottom: 1rem;
  flex: 1;
  min-height: 3rem;
}

.portfolio-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.tag {
  background: rgba(99, 102, 241, 0.1);
  color: #6366f1;
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 500;
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
