<template>
      <nav class="fixed-top navbar navbar-expand-lg navbar-dark bg-dark" aria-label="Tenth navbar example">
    <div class="container-fluid">
      <button class="navbar-toggler collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#navbar" aria-controls="navbarsExample08" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="navbar-collapse justify-content-md-center collapse" id="navbar" style="">
        <ul class="navbar-nav">
          <li class="nav-item" v-for="linkItem in props.menuLinks" :key="linkItem.label">
            <a :class="{ 'barra': linkActive == linkItem.id }" class="nav-link" @click="setActiveLink(linkItem.id)" aria-current="page" :href="`#${linkItem.id}`">{{ linkItem.label }} </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { defineProps, ref } from 'vue';

const linkActive = ref('home')
const setActiveLink = (id) => {
    linkActive.value = id
}
const props = defineProps({
    menuLinks: {
        type: Array,
        required: true
    }
})
</script>

<style scoped>
.barra {
  color: #4CAF50;
}

</style>