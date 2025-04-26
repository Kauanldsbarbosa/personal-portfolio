<template>
  <div id="main" class="bg-black container-fluid d-flex flex-column flex-md-row full-height pt-5">

    <!-- Coluna da esquerda - Imagem -->
    <div class="left-side col-12 col-md-6 d-flex justify-content-center align-items-center">
      <img src="../assets/images/developer_activity-pana.svg" alt="image" class="w-100 object-cover" />
    </div>

    <!-- Coluna da direita - Texto e Ícones -->
    <div :class="{ 'scale-up-center': animated }" class="typing right-side col-12 col-md-6 d-flex flex-column justify-content-center align-items-center text-center p-3">
      <h2 :class="{ 'typing-effect': animated }" class="fs-1" style="font-family: 'Fira Code', serif;">
        <span class="green-color">Hi</span>,i'm Kauan Barbosa.
      </h2>
      <h1 class="text-center" style="font-family: 'Oswald', serif;">
        Web Developer
      </h1>
      <p class="display-4 text-light text-center fs-4 tracking-in-contract-bck"
        style="font-family: 'Afacad Flux', serif;">
        Transform your business. <i :class="{ 'text-flicker-in-glow': animated }" class="green-color">With the solution you are looking for!</i>
      </p>
      <div class="row d-flex justify-content-center align-items-center">
        <a href="https://github.com/Kauanldsbarbosa" target="_blank" rel="noopener noreferrer">
          <img src="../assets/images/github_image.png" alt="github image" class="github-icon" />
        </a>
      </div>
    </div>

  </div>
</template>


<script setup>
import { defineEmits,  ref, onMounted } from 'vue';

const animated = ref(false)
const observeComponent = (el) => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      animated.value = entry.isIntersecting
      emits('IsMain', animated.value)
    },
    {
      root: null,
      threshold: 0.3,
    }
  );
  observer.observe(el);
  return observer;
};

const emits = defineEmits(['IsMain']);

onMounted(() => {
  const mainElement = document.getElementById('main');
  observeComponent(mainElement);
});
</script>

<style scoped>
.github-icon {
  height: 3.125rem;
  width: 3.5rem;
  border-radius: 50%;
}
</style>