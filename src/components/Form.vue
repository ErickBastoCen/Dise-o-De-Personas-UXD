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
<center>
  <img src="https://cdn.icon-icons.com/icons2/1378/PNG/512/avatardefault_92824.png" width="300" height="300">
  <br>
  <br>
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
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Edad
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="edad" type="number" placeholder="10" v-model="edad">
        <p class="text-red-500 text-xs italic">Por favor introduzca su edad.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Estado Civil
        </label>
        <div class="relative">
          <select class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500" id="estadoCivil" v-model="estadoCivil">
            <option>Soltero(a)</option>
            <option>Casado(a)</option>
            <option>Viudo(a)</option>
          </select>
        </div>
        <p class="text-gray-600 text-xs italic">Introduzca su estado civil.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Trabajo
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="trabajo" type="text" placeholder="Product Designer" v-model="trabajo">
        <p class="text-red-500 text-xs italic">Por favor introduzca su trabajo.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Residencia
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="residencia" type="text" placeholder="San josé, California" v-model="residencia">
        <p class="text-red-500 text-xs italic">Por favor introduzca el lugar de residencia.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Cita
        </label>
        <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="cita" type="text" placeholder="El diseño no es solo lo que parece y se siente..." v-model="cita">
        </textarea>
        <p class="text-red-500 text-xs italic">Por favor introduzca su cita.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Autor de la cita
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="citaAutor" type="text" placeholder="Steve Jobs" v-model="citaAutor">
        <p class="text-red-500 text-xs italic">Por favor introduzca el autor de su cita.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Biografía
        </label>
        <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="bio" type="text" placeholder="El diseño no es solo lo que parece y se siente..." v-model="bio">
        </textarea>
        <p class="text-red-500 text-xs italic">Por favor introduzca su biografía.</p>
      </div>
    </div>
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Personalidad 1:
          </label>
          <input type="range" min="0" max="100" id="personalidad01" v-model="personalidad01" class="range" step="1" />
          <br>
          <input type="text" name="personalidad01" v-model="personalidad01" disabled style="text-align:center">
          <p class="text-red-500 text-xs italic">Por favor introduzca su rango de personalidad 1.</p>
        </div>
      </div>
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Personalidad 2:
          </label>
          <input type="range" min="0" max="100" id="personalidad02" v-model="personalidad02" class="range" step="1" />
          <br>
          <input type="text" name="personalidad02" v-model="personalidad02" disabled style="text-align:center">
          <p class="text-red-500 text-xs italic">Por favor introduzca su rango de personalidad 2.</p>
        </div>
      </div>
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Personalidad 3:
          </label>
          <input type="range" min="0" max="100" id="personalidad03" v-model="personalidad03" class="range" step="1" />
          <br>
          <input type="text" name="personalidad03" v-model="personalidad03" disabled style="text-align:center">
          <p class="text-red-500 text-xs italic">Por favor introduzca su rango de personalidad 3.</p>
        </div>
      </div>
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Personalidad 4:
          </label>
          <input type="range" min="0" max="100" id="personalidad04" v-model="personalidad04" class="range" step="1" />
          <br>
          <input type="text" name="personalidad04" v-model="personalidad04" disabled style="text-align:center">
          <p class="text-red-500 text-xs italic">Por favor introduzca su rango de personalidad 4.</p>
        </div>
      </div>
    
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Marcas
        </label>
        <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="marcas" type="text" placeholder="Coca Cola" v-model="marcas">
        <p class="text-red-500 text-xs italic">Por favor introduzca el autor de su marca.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Objetivos
        </label>
        <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="objetivos" type="text" placeholder="El diseño no es solo lo que parece y se siente..." v-model="objetivos">
        </textarea>
        <p class="text-red-500 text-xs italic">Por favor introduzca sus objetivos.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Frustraciones
        </label>
        <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="frustraciones" type="text" placeholder="El diseño no es solo lo que parece y se siente..." v-model="frustraciones">
        </textarea>
        <p class="text-red-500 text-xs italic">Por favor introduzca sus frustraciones.</p>
      </div>
    </div>
    <div class="flex flex-wrap -mx-3 mb-6">
      <div class="w-full px-3">
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
          Motivaciones
        </label>
        <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="motivaciones" type="text" placeholder="El diseño no es solo lo que parece y se siente..." v-model="motivaciones">
        </textarea>
        <p class="text-red-500 text-xs italic">Por favor introduzca sus motivaciones.</p>
      </div>
    </div>




    
  </form>



  <button @click="submit()" type="button"
      class="inline-block rounded-full bg-neutral-800 px-6 pt-2.5 pb-2 text-xs font-medium uppercase leading-normal text-neutral-50 shadow-[0_4px_9px_-4px_#332d2d] transition duration-150 ease-in-out hover:bg-neutral-800 hover:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] focus:bg-neutral-800 focus:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] focus:outline-none focus:ring-0 active:bg-neutral-900 active:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] dark:bg-neutral-900 dark:shadow-[0_4px_9px_-4px_#171717] dark:hover:bg-neutral-900 dark:hover:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)] dark:focus:bg-neutral-900 dark:focus:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)] dark:active:bg-neutral-900 dark:active:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)]">Aceptar</button>
</center>
</template>
  
<style>

</style>
  