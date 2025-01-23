<template>
    <div v-for="skill in skills" :key="skill.id"
      class="card-container w-full flex items-center justify-center "
      >
      
      <div class="card w-52 h-36 rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]">
        <!-- Lado posterior (el reverso donde aparece el skill.name) -->
        <div class="card-back w-full h-full flex items-center justify-center bg-[#111a3e] text-white">
          <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
            {{ skill.name }}
          </h3>
        </div>
        
        <!-- Lado frontal (donde aparece la imagen) -->
        <div class="card-front w-full h-full flex items-center justify-center">
          <img :src="skill.img" alt="Skill Image" class="w-16 h-16 object-contain" />
        </div>
      </div>
      
    </div>
  </template>
<script setup>
import { defineProps } from 'vue';
const props = defineProps({
    skills: {
        type: Array,
        required: true,
        default: () => [] // Valor predeterminado para skills si no se pasa
    }
})
</script>

<style>
/* Contenedor de la tarjeta */
.card-container {
  perspective: 1000px; /* Define la distancia de la cámara para el efecto 3D */
}

/* Tarjeta (contiene tanto el frente como el reverso) */
.card {
  position: relative;
  transform-style: preserve-3d; /* Mantener la estructura 3D para las caras */
  transition: transform 0.6s ease; /* Transición suave al girar */
}



/* Lado frontal de la tarjeta */
.card-front,
.card-back {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  backface-visibility: hidden; /* Esconde el reverso cuando se gira */
  display: flex;
  align-items: center;
  justify-content: center;
}

/* Estilo para el lado frontal (donde estará la imagen) */
.card-front {
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Sombra suave para el frente */
  border-radius: 1rem; /* Bordes redondeados */
}

/* Estilo para el lado posterior (donde estará el texto) */
.card-back {
  transform: rotateY(180deg); /* Gira el reverso 180 grados para que no sea visible */
}

/* Efecto al hacer hover (cuando el ratón pasa por encima de la tarjeta) */
.card-container:hover .card {
  transform: rotateY(180deg); /* Gira la tarjeta 180 grados */
}
</style>