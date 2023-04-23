<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Titulo from "./components/Titulo.vue";
</script>

<template class="flex-col justify-center bg-blue-100 w-full h-full p-2">

<div class="w-full  justify-items-center">
      
      <header>
  
        <nav class ="py-3 bg-black flex justify-self-center items-center text-white pl-5 gap-5 font-semibold hover:text-gray-500">
          <RouterLink to="/">Inicio</RouterLink>
          <RouterLink to="/Registro">Registro</RouterLink>
          <RouterLink to="/Usuarios">Usuario</RouterLink>
        </nav>
        
        <div class="w-full">
  
          <Titulo msg="Hola" />
  
          
        </div>
  
      </header>
  
  
    <RouterView />
  </div>
  </template>