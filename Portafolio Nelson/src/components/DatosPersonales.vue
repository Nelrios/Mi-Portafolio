<script setup>
import linkedin from '../assets/linkedin_icon.svg';
import instagram from '../assets/instagram_icon.svg';
import github from '../assets/github_icon.svg';
import cv from '../assets/cv_resume_icon.svg';

const title = 'Nelson Ríos';
const descripcion = 'Técnico Electromecánico y Técnico Universitario en Programación - UTN';
const residencia = 'Tres de Febrero, Buenos Aires, Argentina';
const presentacion = 'Hola, Bienvenido a mi portafolio de proyectos. Soy un desarrollador web con experiencia en el desarrollo de aplicaciones web y móviles.';
const redesSociales = [
  { id: 1, name: 'linkedin', src: linkedin, url: 'https://www.linkedin.com/in/nelson-r%C3%ADos-ba9403218/' },
  { id: 2, name: 'Instagram', src: instagram, url: 'https://www.instagram.com/nelson_pumpa?igsh=dDFpeGdva2FsMHQy' },
  { id: 3, name: 'github', src: github, url: 'https://github.com/Nelrios' },
  { id: 4, name: 'curriculum', src: cv, url: 'https://www.canva.com/design/DAGU1Pc_BSc/brum6XUx5bJZrq7euvuNXw/view?utm_content=DAGU1Pc_BSc&utm_campaign=designshare&utm_medium=link&utm_source=editor' },
];
const telefono = '+54 9 11 6888-3809';
</script>

<template>
  <section class="datos-personales">
    <div class="card">
      <h1>{{ title }}</h1>
      <h2>{{ descripcion }}</h2>
      <p>{{ presentacion }}</p>
      <ul class="container-lista">
        <li v-for="red in redesSociales" :key="red.id">
          <a :href="red.url"><img class="icon-redsocial" :src="red.src" width="35" :alt="red.name"></a>
        </li>
      </ul>
      <h3>☎ Mi Teléfono personal: {{ telefono }}</h3>
      <h4>{{ residencia }}</h4>
    </div>
  </section>
</template>

<style scoped>
h1 {
  font-size: 2.5rem; /* Ajuste del tamaño de fuente */
  color: aliceblue;
}

h2 {
  font-size: 1.8rem; /* Ajuste del tamaño de fuente */
  color: aliceblue;
}

p {
  font-size: 1rem; /* Ajuste del tamaño de fuente */
  font-weight: 600;
  margin-bottom: 1rem;
  color: aliceblue;
}

.card {
  background-color: rgb(28, 41, 52);
  border-radius: 10px;
  padding: 30px; /* Aumento del padding */
  margin: 10px auto; /* Centra el contenedor */
  text-align: center;
  width: 90%; /* Mantiene el ancho porcentual */
  max-width: 800px; /* Aumento del ancho máximo */
  min-width: 280px;
}

.container-lista {
  display: flex;
  justify-content: center;
  list-style: none;
  padding: 0;
  margin: 0;
  flex-wrap: wrap; /* Permite que los iconos se envuelvan en múltiples líneas */
}

.icon-redsocial {
  align-items: center;
  background-color: aliceblue;
  border-radius: 50%;
  padding: 5px;
  margin: 5px;
  box-shadow: 0 0 5px rgba(95, 124, 205, 0.934);
}

.icon-redsocial:hover {
  background-color: rgb(28, 41, 52);
  box-shadow: 0 0 5px rgba(251, 249, 249, 0.934);
}

h3 {
  font-size: 1.3rem; /* Ajuste del tamaño de fuente */
  font-weight: 500;
}

h4 {
  color: gray;
}

@media (max-width: 600px) {
  h1 {
    font-size: 1.8rem; /* Reducción en pantallas pequeñas */
  }

  h2 {
    font-size: 20px; /* Reducción en pantallas pequeñas */
    font-weight: 700;
    margin-top: 15px;
  }

  p {
    font-size: 0.9rem; /* Reducción en pantallas pequeñas */
  }

  h3 {
    font-size: 1rem; /* Reducción en pantallas pequeñas */
  }

  h4 {
    font-size: 0.9rem; /* Reducción en pantallas pequeñas */
  }

  .icon-redsocial {
    width: 30px; /* Ajuste del tamaño de los iconos en pantallas pequeñas */
    height: 30px;
  }
}
</style>
