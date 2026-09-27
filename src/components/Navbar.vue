<template>
  <nav class="navbar" :class="{ 'is-open': isOpen }">
    <div class="nav-header">
      <span class="logo">MiApp</span>
      <!-- Botón hamburguesa para móviles -->
      <button class="menu-toggle" @click="toggleMenu">☰</button>
    </div>
    <!-- Enlaces de navegación -->
    <div class="nav-links">
      <router-link to="/" @click="closeMenu">Inicio</router-link>
      <router-link to="/about" @click="closeMenu">Acerca de</router-link>
    </div>
  </nav>
</template>
<script setup>
import { ref } from "vue";
const isOpen = ref(false);
const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};
const closeMenu = () => {
  isOpen.value = false;
};
</script>
<style scoped>
/* Estilos Base (Móvil Primero) */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 60px;
  background-color: #2c3e50;
  color: white;
  z-index: 1000;
  transition: height 0.3s ease;
  overflow: hidden;
}
.nav-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  height: 60px;
}
.logo {
  font-weight: bold;
  font-size: 1.2rem;
}
.menu-toggle {
  background: none;
  border: none;
  color: white;
  font-size: 1.5rem;
  cursor: pointer;
}
.nav-links {
  display: flex;
  flex-direction: column;
  background-color: #34495e;
  padding: 10px 0;
}
.nav-links a {
  color: white;
  padding: 15px 20px;
  text-decoration: none;
}
.nav-links a.router-link-active {
  background-color: #41b883;
}
/* Estado abierto en móvil */
.navbar.is-open {
  height: auto;
}
/* Pantallas Grandes (Escritorio) */
@media (min-width: 768px) {
  .navbar {
    width: 250px;
    height: 100vh;
  }
  .menu-toggle {
    display: none;
  }
  .nav-header {
    justify-content: center;
    border-bottom: 1px solid #34495e;
  }
  .nav-links {
    background-color: transparent;
    padding: 20px 0;
  }
}
</style>
