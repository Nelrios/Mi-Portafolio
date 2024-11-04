<template>
  <nav class="navbar">
    <div class="navbar-header">
      <button @click="toggleMenu" class="hamburger" :class="{ active: menuOpen }">
        <span class="bar"></span>
        <span class="bar"></span>
        <span class="bar"></span>
      </button>
    </div>
    <div class="navbar-menu" :class="{ active: menuOpen }">
      <ul class="nav-list">
        <li v-for="nav in navegacion" :key="nav.id">
          <a :href="nav.enlace" class="nav-item">{{ nav.nombre }}</a>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue';

const navegacion = ref([
  { id: 1, nombre: 'Educación', enlace: '#educacion' },
  { id: 2, nombre: 'Experiencia', enlace: '#experiencia' },
  { id: 3, nombre: 'Proyectos', enlace: '#proyectos' },
  { id: 4, nombre: 'Habilidades', enlace: '#habilidades' },
  { id: 5, nombre: 'Intereses', enlace: '#intereses' }
]);

const menuOpen = ref(false);

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value;
};
</script>

<style scoped>
.navbar {
  background-color: var(--vt-c-indigo);
  color: #fff;
  padding: 0.5rem 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar-header {
  display: none; /* Oculta el encabezado en pantallas grandes */
}

.hamburger {
  background: none;
  border: none;
  cursor: pointer;
  display: none; /* Oculta el botón hamburguesa en pantallas grandes */
  flex-direction: column;
  justify-content: space-around;
  height: 30px;
  width: 30px;
}

.hamburger .bar {
  height: 3px;
  width: 100%;
  background-color: white;
  transition: 0.3s;
}

.hamburger.active .bar:nth-child(1) {
  transform: rotate(45deg) translate(5px, 5px);
}

.hamburger.active .bar:nth-child(2) {
  opacity: 0;
}

.hamburger.active .bar:nth-child(3) {
  transform: rotate(-45deg) translate(5px, -5px);
}

.navbar-menu {
  display: flex; /* Muestra el menú en línea en pantallas grandes */
  justify-content: flex-end;
  flex-grow: 1; /* Permite que el menú ocupe el espacio restante */
}

.nav-list {
  list-style: none;
  padding: 0; /* Quitar padding por defecto */
  margin: 0; /* Quitar margen por defecto */
  display: flex; /* Mostrar los ítems en una línea horizontal */
}

.nav-item {
  color: #fff;
  text-decoration: none;
  margin: 0 1rem; /* Espacio entre los botones */
  padding: 10px 15px; /* Espaciado interno para simular botones */
  border: 2px solid transparent; /* Border para el efecto de botón */
  border-radius: 5px; /* Bordes redondeados */
  transition: background-color 0.3s, border-color 0.3s; /* Transiciones suaves */
  font-weight: bold;
}

.nav-item:hover {
  background-color: #bdd6f9;
  border-color: #fff; /* Cambia el borde al hacer hover */
  color: black;
}

@media (max-width: 768px) {
  .navbar-header {
    display: flex; /* Muestra el encabezado en pantallas pequeñas */
  }

  .hamburger {
    display: flex; /* Muestra el botón hamburguesa en pantallas pequeñas */
  }

  .navbar-menu {
    display: none; /* Oculta el menú por defecto en pantallas pequeñas */
    flex-direction: column; /* Coloca los elementos en una columna */
    width: 100%; /* Asegura que ocupe el 100% del ancho */
  }

  .navbar-menu.active {
    display: flex; /* Muestra el menú al hacer clic en hamburguesa */
  }

  .nav-list {
    flex-direction: column; /* Muestra los ítems en columna en pantallas pequeñas */
    width: 100%; /* Asegura que ocupe el 100% del ancho */
  }

  .nav-item {
    margin: 0.5rem 0; /* Añade espacio vertical entre elementos */
    padding: 10px;
    text-align: center; /* Centra los elementos en la columna */
    font-size: 17px;
  }
}
</style>
