<template>
  <div id="app">
    <MenuComponent :menuLinks="menuLinks"/>
    <MainVue/>
    <AboutMeVue/>
    <ProjectsGridVue/>
    <ContactMeVue/>
  </div>
</template>

<script setup>
import MenuComponent from '@/components/MenuComponent.vue'
import MainVue from '@/components/MainComponent.vue';
import AboutMeVue from '@/components/AboutMe.vue';
import ProjectsGridVue from '@/components/projects/ProjectsGrid.vue';
import ContactMeVue from '@/components/ContactMe.vue';
import { onMounted } from 'vue';

onMounted(() => {
  document.title = "Kauanldsb | Dev";
});

const menuLinks = [
  {label: 'Home', id: 'main'},
  {label: 'About me', id: 'about-me'},
  {label: 'Projects', id: 'projects-grid'},
  {label: 'Contact', id: 'contact-me'},
]
</script>

<style scoped>
.full-height {
  min-height: 100vh;
  overflow-x: hidden;
}
</style>
