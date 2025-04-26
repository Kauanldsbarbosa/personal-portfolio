<template>
    <div id="projects-grid"
        class="bg-white container-fluid full-height d-flex justify-content-center align-items-center pt-5">
        <div class="d-flex mt-3 flex-column justify-content-center align-items-center text-center text-md-center pt-1">
            <h2 :class="{ 'tracking-in-expand': animated }" class="fs-1"
                style="color: #198754 ;font-family: 'Anton', serif;">Discover some of my projects</h2>
            <div class="album py-5 ">
                <div :class="{ 'slide-in-bottom': animated }" class="container">
                    <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-3">
                        <div class="col">
                            <ProjectCardVue />
                        </div>
                        <div class="col">
                            <ProjectCardVue />
                        </div>
                        <div class="col">
                            <ProjectCardVue />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import ProjectCardVue from '@/components/projects/ProjectCard.vue'
import { ref, onMounted } from 'vue';

const animated = ref(false)
const observeComponent = (el) => {
    const observer = new IntersectionObserver(
        ([entry]) => {
            animated.value = entry.isIntersecting
        },
        {
            root: null,
            threshold: 0.1,
        }
    );
    observer.observe(el);
    return observer;
};

onMounted(() => {
    const mainElement = document.getElementById('projects-grid');
    observeComponent(mainElement);
});
</script>

<style></style>