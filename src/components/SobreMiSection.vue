<template>
    <section class="text-[#2C2C2C] mt-18" id="about">
        <div class="absolute z-0 top-[93rem] inset-x-0 h-64 flex items-start">
            <div class="h-24 w-64 bg-gradient-to-br text-[#2C2C2C] opacity-20"></div>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 sm:py-16 xl:px-16 z-1">
            <div data-aos="flip-right">
                <h2 class="text-4xl font-bold text-[#2C2C2C] text-left mb-8">Educación</h2>
                <div class="space-y-8 py-8">
                    <div v-for="element in education" :key="element.id"
                        class="flex items-center md:w-[80%] w-full rounded-xl bg-[#8A6FBF] shadow-lg border border-[#2C2C2C] py-4">
                        <div class="w-1/4 pl-3">
                            <img src="https://img.icons8.com/ios-glyphs/60/ffffff/graduation-cap--v1.png"
                                alt="graduation-cap--v1">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3
                                class="text-2xl font-bold uppercase text-transparent bg-clip-text bg-gradient-to-r text-[#2C2C2C] lg:text-xl">
                                {{ element.School }}
                            </h3>
                            <p class="text-[#2C2C2C] font-semibold">{{ element.program }}</p>
                            <p class="text-[#2C2C2C] font-semibold">{{ element.year }}</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full" data-aos="flip-right">
                <h2 class="text-4xl font-bold text-[#2C2C2C] md:text-center text-left mb-4">Sobre
                    <span class="text-transparent bg-clip-text bg-gradient-to-r text-[#8A6FBF]">mi</span>

                </h2>
                <p class="font-semibold text-base lg:text-lg mt-8 py-8">
                    La programación me entusiasma porque me brinda la oportunidad de solucionar problemas complejos de
                    forma creativa y mejorar la experiencia de los usuarios. Siempre estoy en la búsqueda de nuevas
                    tecnologías y métodos para seguir avanzando en mi carrera profesional.
                </p>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
const education = ref([
    {
        id: 1,
        School: 'IES Virgen del Carmen',
        program: 'Desarrollo de Aplicaciones Multiplataforma',
        year: '2023'
    },

])
</script>