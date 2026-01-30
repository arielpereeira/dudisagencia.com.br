<template>
  <nav class="navbar navbar-expand-lg navbar-dark fixed-top" :class="{ 'navbar-scrolled': scrolled || !isHome }">
    <div class="container">
      <router-link class="navbar-brand fw-bold" to="/">
        <span class="logo-text">DUDIS</span>
      </router-link>
      <button 
        class="navbar-toggler" 
        type="button" 
        data-bs-toggle="collapse" 
        data-bs-target="#navbarNav"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link" href="/#home">Início</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/#services">Serviços</a>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/portfolio">Portfólio</router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="/#about">Sobre</a>
          </li>
          <li class="nav-item">
            <a class="nav-link btn-contact" href="/#contact">Contato</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted, computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const scrolled = ref(false)

const isHome = computed(() => route.path === '/')

const handleScroll = () => {
  scrolled.value = window.scrollY > 50
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
.navbar {
  background: transparent;
  transition: all 0.4s ease;
  padding: 1.5rem 0;
}

.navbar-scrolled {
  background: rgba(30, 41, 59, 0.95) !important;
  backdrop-filter: blur(10px);
  padding: 1rem 0;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
}

.logo-text {
  font-size: 1.8rem;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-weight: 800;
  letter-spacing: 2px;
}

.nav-link {
  color: rgba(255, 255, 255, 0.9) !important;
  font-weight: 500;
  margin: 0 0.5rem;
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 2px;
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  transition: width 0.3s ease;
}

.nav-link:hover::after {
  width: 80%;
}

.btn-contact {
  background: linear-gradient(135deg, #6366f1 0%, #8b5cf6 100%);
  padding: 0.5rem 1.5rem !important;
  border-radius: 25px;
  margin-left: 1rem;
  -webkit-text-fill-color: white !important;
}

.btn-contact::after {
  display: none;
}

.btn-contact:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(99, 102, 241, 0.4);
}
</style>
