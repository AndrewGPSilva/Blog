<template>
  <nav class="bg-black p-2 flex flex-col">
    <div class="flex justify-between items-center m-4">
      <router-link to="/"><img class="w-4/4 h-20" src="../../assets/logo.jpg" alt="Logo do Blog" /></router-link>
      <button @click="showMenu" v-if="!ativado">
        <i class="pi pi-align-justify" style="color: orange; font-size: 2rem"></i>
      </button>
      <button @click="showMenu" v-if="ativado">
        <i class="pi pi-minus" style="color: orange; font-size: 2rem"></i>
      </button>
    </div>
    <div class="animation" v-show="ativado">
      <ul class="text-white m-4 flex flex-col text-end">
        <router-link to="/" class="flex justify-end">
          <li class="bg-orange-500 text-white p-1 text-center m-1 rounded-lg w-2/5 font-bold">
            Home
          </li>
        </router-link>
        <router-link to="/backend" class="flex justify-end">
          <li class="bg-orange-500 text-white p-1 text-center m-1 rounded-lg w-2/5 font-bold">
            Back-End
          </li>
        </router-link>
        <router-link to="/frontend" class="flex justify-end">
          <li class="bg-orange-500 text-white p-1 text-center m-1 rounded-lg w-2/5 font-bold">
            Front-End
          </li>
        </router-link>
        <router-link to="/artigos" class="flex justify-end">
          <li class="bg-orange-500 text-white p-1 text-center m-1 rounded-lg w-2/5 font-bold">
            Artigos Tech
          </li>
        </router-link>
      </ul>
    </div>
  </nav>
  <Line />
</template>

<script setup>
import { ref } from 'vue';
import Line from './Line.vue';

const ativado = ref(false);

function showMenu() {
  ativado.value = !ativado.value;
  console.log(ativado.value);
}
</script>

<style scoped>
.animation {
  animation: slideInRight;
  animation-duration: 0.5s;
}

li:hover {
  background-color: rgb(91, 206, 206);
  color: black;
  font-weight: bold;
}
</style>