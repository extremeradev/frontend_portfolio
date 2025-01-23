<template>
    <section class="text-[#2C2C2C] mt-20" id="services">
        <div class="px-4 xl:pl-16">
            <h2 class="text-4xl font-bold text-[#2C2C2C] mb-4">Habilidades</h2>
        </div>
        <div
            class="py-8 xl:px-16 px-4 sm:py-16 grid grid-cols-1 gap-6 pt-10 sm:grid-cols-2 md:gap-10 md:pt-12 lg:grid-cols-3">
            <div v-for="service in services" :key="service.id" data-aos="fade-up"
                class="px-8 py-12 rounded-xl bg-[#8A6FBF] shadow-lg border border-[#2C2C2C]">
                <div class="mx-auto h-24 w-24 text-center xl:h-28 xl:w-28">
                    <div>
                        <img :src="service.icon" alt="service icon">
                    </div>
                </div>
                <div class="text-center">
                    <h3
                        class="pt-8 text-lg font-bold uppercase bg-clip-text bg-gradient-to-r text-[#2C2C2C] lg:text-xl">
                        {{ service.name }}
                    </h3>
                    <p class="text-[#2C2C2C] font-semibold pt-4 text-sm group-hover:text-white md:text-base">
                        {{ service.description }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
const services = ref([
    {
        id: 1,
        icon: 'https://img.icons8.com/ios-filled/100/ffffff/google-code.png',
        name: 'DESARROLLO WEB',
        description: 'Creación de aplicaciones web interactivas y escalables.'
    },
    {
        id: 2,
        icon: 'https://img.icons8.com/?size=100&id=11138&format=png&color=ffffff',
        name: 'DESARROLLO MÓVIL',
        description: 'Desarrollo de aplicaciones móviles con patrón de arquitectura MVVM y MVC.'
    },
    {
        id: 3,
        icon: 'https://img.icons8.com/?size=100&id=22803&format=png&color=ffffff',
        name: 'SOLUCIONES WEB',
        description: 'Desarrollo aplicaciones backend robustas y escalables asegurando eficiencia, seguridad y un alto rendimiento.'
    },
])
</script>