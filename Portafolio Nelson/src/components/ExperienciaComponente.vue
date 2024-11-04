<script setup>
import icono1 from '../assets/grupo.png';
import icono2 from '../assets/web.png';

import { ref } from 'vue';
const titulo = 'Desarrollador Full Stack';
const fecha = 'Desde Enero 2022 / Octubre 2024';
const experiencias = ref([
    { id: 1, src: icono1, parrafo: 'Forme parte de proyectos grupales en los cursos de formación de programación, incursionando en diferentes bibliotecas, frameworks y tecnologías de desarrollo web.' },
    { id: 2, src: icono2, parrafo: 'Desarrollé aplicaciones web utilizando Node.js, Vue.js, HTML, CSS. Formando parte del diseño, la ejecución y el testeo.' },
]);
</script>

<template>
    <div class="card">
        <h3 class="titulo">{{ titulo.toLocaleUpperCase() }}</h3>
        <p class="fecha">{{ fecha }}</p>
        <ul class="listado">
            <li class="item" v-for="experiencia in experiencias" :key="experiencia.id">
                <img class="imagen-svg" :src="experiencia.src" :alt="experiencia.parrafo">
                <p>{{ experiencia.parrafo }}</p>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    padding: 1.5rem; /* Ajuste del padding */
    background-color: rgb(28, 41, 52);
    border-radius: 15px;
    max-width: 95%; /* Cambiado a 95% para ser un poco más ancho */
    min-width: 280px; /* Añadido un ancho mínimo para pantallas pequeñas */
    margin: 20px auto; /* Centra la tarjeta y agrega un margen */
}

.imagen-svg {
    width: 60px; /* Ajuste de tamaño para pantallas pequeñas */
    height: auto;
    margin-right: 1rem;
}

.titulo {
    font-size: 1.5rem;
    color: coral;
    text-align: center; /* Centra el título */
}

.fecha {
    font-size: 1rem;
    color: burlywood;
    margin-bottom: 1rem;
    text-align: center; /* Centra la fecha */
}

.listado {
    display: flex;
    flex-direction: column;
    padding: 0; /* Eliminar padding extra */
}

.item {
    align-items: flex-start; /* Cambiar a flex-start para mejor alineación */
    display: flex;
    padding: 0.5rem; /* Ajuste del padding */
    gap: 1rem; /* Espacio entre icono y texto */
    font-size: 1rem; /* Ajuste de tamaño de fuente para pantallas pequeñas */
    color: aliceblue;
}

@media (max-width: 600px) {
    .titulo {
        font-size: 22px; /* Reducción en pantallas pequeñas */
    }
    .fecha {
        font-size: 0.9rem; /* Reducción en pantallas pequeñas */
    }
    .item {
        font-size: 0.9rem; /* Reducción en pantallas pequeñas */
        overflow: visible;
    }
    .imagen-svg {
        width: 40px; /* Ajuste de tamaño para pantallas pequeñas */
    }
}
</style>

