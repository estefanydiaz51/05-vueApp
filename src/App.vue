<template>
  <!-- <HelloWorld msg="perro bambaro"></HelloWorld>
  <input type="text" name="" v-model="nombre">
  <p>{{ saludar }}</p>
  <form-data></form-data> -->
  <suspense>
    <template #default>
        <Pokemones></Pokemones>
    </template>
    <template #fallback>
        Loading...
    </template>
</suspense>
</template>

<script setup>
// import { ref } from '@vue/reactivity'
// import { computed } from '@vue/runtime-core';
// import HelloWorld from './components/HelloWorld.vue';
// import FormData from './components/FormData.vue';
import Pokemones from './components/Pokemones.vue';

// export default {
//   name: 'App',
//   components: {
//     HelloWorld
//   }
// }

  // const nombre = ref('');
  // const saludar = computed( () => {
  //   return !nombre.value.trim() ? 'Invitado' : nombre.value;
  // })
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
