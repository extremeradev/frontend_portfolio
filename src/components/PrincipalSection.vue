<template>
    <section class="relative w-full" data-aos="zoom-in-up">
        <div class="absolute top-0 inset-x-0 h-64 flex items-start">
            <div class="h-24 w-3/3 bg-gradient-to-br from-[#8A6FBF] blur-2xl invisible opacity-40"></div>
            <div class="h-20 w-3/5 bg-gradient-to-r from-[#8A6FBF] opcity-40 blur-2xl"></div>
        </div>
        <div class="w-full px-5 sm:px-8 md:px-12 lg:px-8 max-w-screen-lg lg:max-w-screen-xl mx-auto relative">
            <div
                class="grid lg:grid-cols-2 gap-10 xl:gap-14 relative pt-24 lg:max-w-none max-w-2xl md:max-w-3xl mx-auto">
                <div class="lg:py-6">
                    <div class="text-center lg:text-left">
                        <h1 class="pt-4 text-[#2C2C2C] font-bold text-4xl md:text-5xl lg:text-5xl">
                            Hola, soy <span class=" bg-clip-text bg-gradient-to-r text-[#8A6FBF]">
                                Alejandro
                            </span>
                        </h1>
                    </div>
                    <p class="text-[#2C2C2C] font-semibold pt-8 text-center lg:text-left mx-auto max-w-xl">
                        Me apasiona la tecnología y programar para hacer que las ideas cobren vida a través del código,
                        buscando siempre la forma más eficiente de hacerlo.
                    </p>
                    <div class="flex items-center gap-3 pt-9 flex-col sm:flex-row sm:w-max sm:mx-auto lg:mx-0">
                    </div>
                </div>
                <div class="lg:h-full md:flex">
                    <div
                        class="flex w-full h-96 min-h-[24rem] lg:min-h-[none] lg:w-full lg:h-full items-center relative">
                        <div
                            class="absolute z-0 top-1/2 -translate-y-1/2 w-5/6 right-0 h-[calc(80%+20px)] bg-gradient-to-tr opacity-25 from-[#8A6FBF] blur-2xl">
                        </div>
                        <div class="max-w-[200px] h-[200px] absolute z-10 p-1 -translate-y-1/2 top-1/3 left-1/2 -translate-x-1/2 
                                    sm:max-w-[400px] sm:h-[400px] sm:translate-x-0 sm:left-auto sm:right-16 
                                    md:right-40 lg:right-3 rounded-full shadow-lg border border-[#8A6FBF]">
                            <img src="@/assets/profile.jpg" alt="Hero pic" width="500" height="auto" loading="lazy"
                                class="w-full h-full rounded-full object-cover">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import AOS from 'aos';
import 'aos/dist/aos.css';
AOS.init();
</script>