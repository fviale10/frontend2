<template>
  <div class="app-layout">
    <!-- El menú siempre fijo -->
    <Navbar />
    <!-- El contenido que va cambiando -->
    <main class="main-content">
      <router-view />
    </main>
  </div>
</template>
<script setup>
import Navbar from "./components/Navbar.vue";
</script>
<style>
/* Reset básico */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  font-family: sans-serif;
  background-color: #f5f7fa;
}
/* Layout responsivo */
.app-layout {
  display: flex;
  flex-direction: column;
}
.main-content {
  flex: 1;
  padding: 20px;
  margin-top: 60px;
}
/* Ajuste para pantallas grandes (Escritorio) */
@media (min-width: 768px) {
  .app-layout {
    flex-direction: row;
  }
  .main-content {
    margin-top: 0;
    margin-left: 250px;
    min-height: 100vh;
  }
}
</style>
