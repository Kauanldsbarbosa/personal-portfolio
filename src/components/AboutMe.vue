<template>
    <div id="about-me" class="full-height bg-black-aternative container-fluid d-flex justify-content-center align-items-center">
        <div :class="{ 'scale-up-center': animated }" class="col-lg-6 w-50 ml-1 mt-3">
            <h2 class="display-5 fw-bold lh-1 mb-3 text-center neon-text green-color">About me</h2>
            <p class="lead text-white text-center" style="font-family: 'Oswald', serif;">I'm Kauan Barbosa, a web
                programmer
                passionate about technology. I currently work at
                Altsystems, where I am
                dedicated to offering the best solutions for each project. I am always looking to improve my skills and
                I am
                committed to delivering my best in everything I do, facing challenges and creating innovative solutions
                that
                add value.</p>
            <hr class="mb-3">
            <div class="d-grid gap-2 d-md-flex justify-content-md-center mt-3">
                <div class="container">
                    <h3 class="fs-1 text-center green-color mb-3" style="font-family: 'Oswald', serif;">Get to know some
                        of my
                        skills</h3>
                    <div class="row d-flex justify-content-center align-items-center my-1">
                        <div class="col-12 col-md-2 mt-2">
                            <img src="@/assets/logo.png" alt="Imagem 1" class="img-fluid">
                        </div>
                        <div class="col-12 col-md-2 mt-2">
                            <img src="@/assets/nuxt.svg" alt="Imagem 2" class="img-fluid">
                        </div>
                        <div class="col-12 col-md-2 mt-2">
                            <img src="@/assets/docker.svg" alt="Imagem 3" class="img-fluid">
                        </div>
                        <div class="col-12 col-md-2 mt-2">
                            <img src="@/assets/fastapi.svg" alt="Imagem 3" class="img-fluid">
                        </div>
                    </div>
                    <h3 class="fs-1 text-center green-color mt-3" style="font-family: 'Oswald', serif;">And others.</h3>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
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
  const mainElement = document.getElementById('about-me');
  observeComponent(mainElement);
});
</script>

<style></style>