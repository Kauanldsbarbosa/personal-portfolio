<template>
  <div id="contact-me" class="full-height bg-black container-fluid d-flex justify-content-center align-items-center">
    <div :class="{ 'tracking-in-expand': animated }" class=" ml-1 mt-3">
      <h2 class="display-5 fw-bold lh-1 mb-3 text-center mb-4">Contact <span class="green-color">me</span></h2>
      <div class="d-flex gap-4 flex-wrap justify-content-center align-items-center">
        <a :href="discordChannel" target="_blank"> <span class="fs-5 text-nowrap"><i class="fa fa-discord"></i> kauanldsbarbosa</span></a>
        <a :href="`mailto:kauanldsbarbosa@gmail.com?subject=${emailSubject}`" :subject="emailMessage"><span class="fs-5"><i class="fa fa-envelope"></i>
            kauanldsbarbosa@gmail.com</span></a>
        <a :href="linkedinLink" target="_blank"><span class="fs-5 text-nowrap"><i class="fa fa-linkedin"></i> kauanldsbarbosa</span></a>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const emailSubject = ref('Interested in learning more about your services.')
const discordChannel = ref('https://discord.gg/p56YY6gF')
const linkedinLink = ref('https://www.linkedin.com/in/kauanldsbarbosa/')

const animated = ref(false)
const observeComponent = (el) => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      animated.value = entry.isIntersecting
    },
    {
      root: null,
      threshold: 0.4,
    }
  );
  observer.observe(el);
  return observer;
};

onMounted(() => {
  const mainElement = document.getElementById('contact-me');
  observeComponent(mainElement);
});
</script>

<style>
#contact-me a {
  text-decoration: none;
  color: inherit;
  pointer-events: auto;
}
</style>