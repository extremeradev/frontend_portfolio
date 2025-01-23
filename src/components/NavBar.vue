<template>
  <header class="flex justify-between items-center p-6 bg-opacity-50 relative z-20">
    <div class="text-[#2C2C2C] text-1xl font-bold">
      <h4
        class="text-[16px] sm:text-[14px] md:text-[18px] lg:text-[24px] text-transparent bg-clip-text text-[#2C2C2C] font-bold">
        (+34) 722 64 81 73 · <br />
        extremera.dev@gmail.com
      </h4>
    </div>

    <!-- Mobile Toggle Button-->
    <div class="md:hidden z-30">
      <button type="button" class="block focus:outline-none" @click="toggleMenu">
        <span v-if="isMenuOpen" class="text-5xl">
          <img src="https://img.icons8.com/ios-filled/100/2c2c2c/delete-sign.png" alt="close" width="50" height="50">
        </span>
        <span v-else class="text-5xl">
          <img src="https://img.icons8.com/ios-filled/100/2c2c2c/menu--v6.png" alt="menu" width="50" height="50">
        </span>
      </button>
    </div>

    <!-- Navbar Link-->
    <nav :class="['fixed inset-0 z-20 flex flex-col items-center justify-center bg-[#7F6A9D] md:relative md:bg-transparent md:flex md:justify-between md:flex-row',
      isMenuOpen ? 'block' : 'hidden'
    ]">
      <ul class="flex flex-col items-center space-y-5 md:flex-row md:space-x-5 md:space-y-0">
        <li v-for="item in Menu" :key="item.name">
          <a :href="item.href"
            class="block text-[#2c2c2c] font-bold transition hover:text-[#7F6A9D] ease-linear text-2xl md:text-lg"
            @click="scrollToSection(item.href)">
            {{ item.name }}
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
import { ref } from 'vue';

const Menu = ref([
  { name: 'Habilidades', href: '#services' },
  { name: 'Sobre mi', href: '#about' },
  { name: 'Tecnologías', href: '#skills' },
  { name: 'Contacto', href: '#contact' },
]);

const isMenuOpen = ref(false);

// Función para abrir y cerrar el menú
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  if (isMenuOpen.value) {
    disableScroll();
  } else {
    enableScroll();
  }
}

// Función para deshabilitar el scroll
const disableScroll = () => {
  // Deshabilitar scroll en html y body
  document.documentElement.style.overflow = 'hidden';
  document.body.style.overflow = 'hidden';
  document.body.style.position = 'fixed';  // Fijar la posición de la página
  document.body.style.top = `-${window.scrollY}px`;  // Evitar que la página se mueva
}

// Función para habilitar el scroll
const enableScroll = () => {
  document.documentElement.style.overflow = 'auto';
  document.body.style.overflow = 'auto';
  document.body.style.position = '';  // Restaurar posición
  document.body.style.top = '';  // Restaurar la posición anterior
  window.scrollTo(0, parseInt(document.body.style.top || '0', 10));  // Restaurar el scroll
}

// Función para hacer scroll a la sección
const scrollToSection = (href) => {
  isMenuOpen.value = false;
  enableScroll();
  const section = document.querySelector(href);
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
  }
}
</script>