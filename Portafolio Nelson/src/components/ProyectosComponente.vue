<script setup>
import proyecto1 from '../assets/Quiron.png';
import proyecto2 from '../assets/WebAG.png';
import proyecto3 from '../assets/WebAG2.png';
import proyecto4 from '../assets/e-commerce.png';

import { ref } from 'vue';
var misProyectos = ref([]);
misProyectos.value = ([
    {
        id: 1,
        src: proyecto1,
        titulo: "Aplicación Móvil para Quiron Gym.",
        descripcion: "Creé una aplicación móvil de gestión para un gimnasio donde los usuarios y el administrador pueden crear perfiles y manejar horarios y pagos. Incluí APIs y bases de datos",
    },
    {
        id: 2,
        src: proyecto2,
        titulo: "Plataforma Web - Profesora de español.",
        descripcion: "Diseñé y desarrollé una página web para una profesora de español para extranjeros. El desarrollo lo implementé usando herramientas como HTML, CSS y Javascript."
    },
    {
        id: 3,
        src: proyecto3,
        titulo: "Página Web para aprendizaje de español especial para extranjeros.",
        descripcion: "Diseñé y desarrollé una página web para aprendizaje de español para extranjeros. El desarrollo lo implementé usando herramientas como HTML, CSS y Javascript."
    },
    {
        id: 4,
        src: proyecto4,
        titulo: "E-commerce Relojería",
        descripcion: "Participé en un grupo de diseño y desarrollo de un E-commerce para una relojería. Implementamos APIs y distintas tecnologías y lenguajes de programación."
    },
]);
</script>

<template>
    <div class="galeria">
        <ul>
            <li class="proyecto" v-for="proyecto in misProyectos" :key="proyecto.id">
                <img :src="proyecto.src" :alt="proyecto.titulo">
                <div class="proyecto-info">
                    <h3>{{ proyecto.titulo }}</h3>
                    <p>{{ proyecto.descripcion }}</p>
                </div>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.galeria {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    padding: 20px;
    justify-content: center;
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
    background-size: 400% 400%;
    animation: gradient 15s ease infinite;
    border-radius: 20px;
    min-width: 280px;
}

@keyframes gradient {
    0% { background-position: 0% 50%; }
    50% { background-position: 100% 50%; }
    100% { background-position: 0% 50%; }
}

.proyecto {
    display: flex;
    flex-direction: column;
    border: 2px solid #ddd;
    border-radius: 8px;
    overflow: hidden;
    background-color: #d0d0d0;
    flex: 1 1 300px; /* Permite que el contenedor ocupe al menos 300px */
    margin-bottom: 1rem;
}

.proyecto img {
    width: 100%; /* Ajusta al 100% del contenedor */
    height: auto; /* Mantiene la proporción */
    object-fit: cover;
    display: block;
    border-radius: 15px 15px 0 0; /* Redondeo solo en la parte superior */
}

.proyecto-info {
    padding: 15px;
    text-align: center;
}

.proyecto-info h3 {
    margin: 10px 0;
    font-size: 20px; /* Ajuste de tamaño de fuente */
    color: #000;
    font-weight: bold;
}

.proyecto-info p {
    margin: 10px 0;
    font-size: 18px; /* Ajuste de tamaño de fuente */
    color: #191919;
}

@media (max-width: 600px) {
  h3 {
  font-size: 20px; /* Reducción en pantallas pequeñas */
  font-weight: bold;
  }

  p {
  font-size: 18px; /* Reducción en pantallas pequeñas */
  }

.galeria {
  flex-direction: column; /* Apilar elementos en pantallas pequeñas */
  align-items: center; /* Centrar elementos en el contenedor */
  justify-content: center;
  padding: 10px; /* Ajuste de padding en pantallas pequeñas */
    }

.proyecto {
  width: 100%; /* Asegura que cada proyecto ocupe todo el ancho disponible */
  max-width: none; /* Elimina el máximo ancho en pantallas pequeñas */
    }
}
</style>
