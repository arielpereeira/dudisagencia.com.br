<template>
  <footer class="footer bg-dark text-light py-5">
    <div class="container">
      <div class="row">
        <div class="col-md-4 mb-4">
          <h3 class="logo-text mb-3">DUDIS</h3>
          <p class="footer-description">
            Agência digital especializada em transformar ideias em experiências digitais incríveis.
          </p>
          <div class="social-links mt-3">
            <a href="#" class="me-3"><i class="bi bi-facebook"></i></a>
            <a href="#" class="me-3"><i class="bi bi-instagram"></i></a>
            <a href="#" class="me-3"><i class="bi bi-linkedin"></i></a>
            <a href="#"><i class="bi bi-twitter"></i></a>
          </div>
        </div>
        <div class="col-md-4 mb-4">
          <h5 class="mb-3 text-light">Links Rápidos</h5>
          <ul class="list-unstyled">
            <li><a href="#home">Início</a></li>
            <li><a href="#services">Serviços</a></li>
            <li><a href="#portfolio">Portfólio</a></li>
            <li><a href="#about">Sobre</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </div>
        <div class="col-md-4 mb-4">
          <h5 class="mb-3 text-light">Contato</h5>
          <ul class="list-unstyled footer-contact">
            <li class="mb-2">
              <i class="bi bi-envelope me-2"></i>
              contato@dudis.com.br
            </li>
            <li class="mb-2">
              <i class="bi bi-phone me-2"></i>
              (11) 9999-9999
            </li>
            <li class="mb-2">
              <i class="bi bi-geo-alt me-2"></i>
              São Paulo, SP
            </li>
          </ul>
        </div>
      </div>
      <hr class="my-4 border-secondary">
      <div class="row">
        <div class="col-md-12 text-center">
          <p class="footer-copyright mb-0">
            &copy; {{ currentYear }} Dudis Agência Digital. Todos os direitos reservados.
          </p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const currentYear = computed(() => new Date().getFullYear())
</script>

<style scoped>
.footer {
  margin-top: 5rem;
}

.logo-text {
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800;
  letter-spacing: 2px;
}

.footer a {
  color: #94a3b8;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer a:hover {
  color: #6366f1;
}

.footer-description {
  color: #94a3b8;
  line-height: 1.6;
}

.footer-contact {
  color: #94a3b8;
}

.footer-copyright {
  color: #64748b;
}

.social-links a {
  font-size: 1.5rem;
  display: inline-block;
  transition: transform 0.3s ease;
  color: #94a3b8;
}

.social-links a:hover {
  transform: translateY(-3px);
  color: #6366f1;
}

.list-unstyled li {
  margin-bottom: 0.5rem;
}

h5 {
  color: white;
  font-weight: 700;
}
</style>
