<template>
  <div class="bg-[#111827] min-h-screen">
    <NavBar />
    <PrincipalSection />
    <ServiciosSection />
    <SobreMiSection />
    <SkillsSection />
    <ContactoSection />
    <FooterSection />
    
  </div>
</template>

<script setup>
import { defineAsyncComponent} from 'vue';

//Import components asynchronously
const NavBar = defineAsyncComponent(() => import('@/components/NavBar.vue'))
const PrincipalSection = defineAsyncComponent(() => import('@/components/PrincipalSection.vue'))
const ServiciosSection = defineAsyncComponent(() => import('@/components/ServiciosSection.vue'))
const SobreMiSection = defineAsyncComponent(() => import('@/components/SobreMiSection.vue'))
const SkillsSection = defineAsyncComponent(() => import('@/components/SkillsSection.vue'))
const ContactoSection = defineAsyncComponent(() => import('@/components/ContactoSection.vue'))
const FooterSection = defineAsyncComponent(() => import('@/components/FooterSection.vue'))
</script>
