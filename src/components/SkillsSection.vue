<template>
    <section class="text-[#2C2C2C] mt-18" id="skills">
        <div class="absolute right-0 top-[110rem] w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-8 px-4 xl:gap-16 xl:px-16">

            <div class="w-full mx-0 px-0 mt-4 md:mt-0 text-left flex flex-col z-10 h-full" data-aos="fade-left">
                <h2 class="text-4xl font-bold text-[#2C2C2C] text-left mb-4">Tecnologías
                    <span class="text-transparent bg-clip-text bg-gradient-to-r text-[#8A6FBF]">Destacadas</span>
                </h2>
                <div class="grid grid-cols-2 sm:grid-cols-2 lg:grid-cols-3 gap-x-2 gap-y-4 py-8 items-stretch">
                    <SkillCard :skills="Skills" />
                </div>
            </div>

            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-[#2C2C2C] text-left mb-8 md:text-center md:mt-0 mt-8">Experiencia
                    <span class="text-transparent bg-clip-text bg-gradient-to-r text-[#8A6FBF]">Laboral</span>
                </h2>

                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="element in Experinces" :key="element.id"
                        class="flex items-center rounded-xl p-4 bg-[#8A6FBF] shadow-lg border border-[#2C2C2C]">
                        <div class="w-1/4">
                            <img src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png" alt="lawyer">
                        </div>
                        <div class="w-3/4 pl-4">
                            <h3
                                class="text-2xl font-bold uppercase text-transparent bg-clip-text bg-gradient-to-r text-[#2C2C2C]">
                                {{ element.role }}
                            </h3>
                            <p class="text-[#2C2C2C] font-semibold">{{ element.company }}</p>
                            <p class="text-[#2C2C2C] font-semibold">{{ element.date }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { ref } from 'vue';
import SkillCard from '@/components/SkillCard.vue';

const Skills = ref([
    {
        id: 1,
        name: 'Java',
        img: "https://img.icons8.com/?size=100&id=13679&format=png&color=000000"
    },
    {
        id: 2,
        name: 'Spring',
        img: "https://img.icons8.com/?size=100&id=90519&format=png&color=000000"
    },
    {
        id: 3,
        name: 'JavaScript',
        img: "https://img.icons8.com/?size=100&id=PXTY4q2Sq2lG&format=png&color=000000"
    },
    {
        id: 4,
        name: 'jQuery',
        img: "https://img.icons8.com/?size=100&id=zh7me4lnKerp&format=png&color=000000"
    },
    {
        id: 5,
        name: 'CSS3',
        img: "https://img.icons8.com/?size=100&id=21278&format=png&color=000000"
    },
    {
        id: 6,
        name: 'HTML5',
        img: "https://img.icons8.com/?size=100&id=23028&format=png&color=000000"
    },
    {
        id: 7,
        name: 'Git',
        img: "https://img.icons8.com/?size=100&id=20906&format=png&color=000000"
    },
    {
        id: 8,
        name: 'SQL',
        img: "https://img.icons8.com/?size=100&id=uHZV38hOzCFA&format=png&color=000000"
    },
    {
        id: 9,
        name: 'Android',
        img: "https://img.icons8.com/?size=100&id=17836&format=png&color=000000"
    },
    {
        id: 10,
        name: 'Jenkins',
        img: "https://img.icons8.com/?size=100&id=39292&format=png&color=000000"
    },

]);

const Experinces = ref([
    {
        id: 1,
        role: 'Desarrollador web',
        company: 'Indra - Minsait',
        date: 'Mayo 2024 - Actualidad'
    },
    {
        id: 2,
        role: 'Desarrollador multiplataforma',
        company: 'Petroprix - Wipay',
        date: 'Marzo 2023 - Mayo 2024'
    },
]);

// Propiedades para el modal
const isVisible = ref(false);
const skillName = ref('');

const openModal = (name) => {
    skillName.value = name;
    isVisible.value = true;
};

const closeModal = () => {
    isVisible.value = false;
};


</script>

<style scoped>
.modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.5);
    display: flex;
    justify-content: center;
    align-items: center;
}

.modal-content {
    background-color: white;
    padding: 20px;
    border-radius: 5px;
}
</style>