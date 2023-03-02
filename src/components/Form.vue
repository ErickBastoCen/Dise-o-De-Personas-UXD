<script>
  import axios from 'axios'
  export default {
    name: 'Form',
    data(){
      return{
        nombre: [],
        edad: [],
        estadoCivil: [],
        trabajo: [],
        residencia: [],
        cita: [],
        citaAutor: [],
        bio: [],
        personalidad01: [],
        personalidad02: [],
        personalidad03: [],
        personalidad04: [],
        objetivos: [],
        frustraciones: [],
        motivaciones: [],
        marcas: []
        }
    },
  methods:{
        submit(){
          axios.post("/api/guardarPersonasUxd.php", {

            nombre: this.nombre,
            edad: this.edad,
            estadoCivil: this.estadoCivil,
            trabajo: this.trabajo,
            residencia: this.residencia,
            cita: this.cita,
            citaAutor: this.citaAutor,
            bio: this.bio,
            personalidad01: this.personalidad01,
            personalidad02: this.personalidad02,
            personalidad03: this.personalidad03,
            personalidad04: this.personalidad04,
            objetivos:this.objetivos,
            frustraciones: this.frustraciones,
            motivaciones: this.motivaciones,
            marcas: this.marcas,

          }).then((response) => {console.log(response.status)});
        }
      }
    }

</script>

<template>
  <form class="w-full max-w-lg">
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Nombres
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="nombre" type="text" placeholder="Juan" v-model="nombre">
        <p class="text-red-500 text-xs italic">Por favor introduzca su nombre.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
          Edad
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="grid-first-name" type="number" placeholder="10" v-model="edad">
        <p class="text-red-500 text-xs italic">Por favor introduzca su edad.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-state">
            Estado Civil
        </label>
        <div class="relative">
          <select class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-state" v-model="estadoCivil">
            <option>Soltero(a)</option>
            <option>Casado(a)</option>
            <option>Viudo(a)</option>
          </select>
        </div>
        <p class="text-gray-600 text-xs italic">Introduzca su estado civil.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
          Trabajo
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="grid-first-name" type="text" placeholder="Juan">
        <p class="text-red-500 text-xs italic">Por favor introduzca su trabajo.</p>
      </div>
    </div>


    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-password">
          Contraseña
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="grid-password" type="password" placeholder="****************">
        <p class="text-gray-600 text-xs italic">Introduzca una contraseña que contenga una Mayúscula, Miniscula, Número y un cáracter especial.</p>
      </div>
    </div>
  </form>
  <button @click="submit()" type="button"
      class="inline-block rounded-full bg-neutral-800 px-6 pt-2.5 pb-2 text-xs font-medium uppercase leading-normal text-neutral-50 shadow-[0_4px_9px_-4px_#332d2d] transition duration-150 ease-in-out hover:bg-neutral-800 hover:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] focus:bg-neutral-800 focus:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] focus:outline-none focus:ring-0 active:bg-neutral-900 active:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] dark:bg-neutral-900 dark:shadow-[0_4px_9px_-4px_#171717] dark:hover:bg-neutral-900 dark:hover:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)] dark:focus:bg-neutral-900 dark:focus:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)] dark:active:bg-neutral-900 dark:active:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)]">Aceptar</button>
</template>
  
<style>

</style>
  