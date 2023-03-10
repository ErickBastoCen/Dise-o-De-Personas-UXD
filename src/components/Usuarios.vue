<script>
import axios from 'axios';


export default {

  data() {
    return {
      personas: [],

      buscar:"",
      buscados: [],
      mostrarBuscadoID: false,
      mostrarBuscados: false

    }
  },


  mounted() {
    
    axios
      .get('/api/getPersonasUxd.php').then((response) => {this.personas = response.data.personas;console.log(response.status)});
        },
  methods: {

    //funcion para buscar personajes
    buscador(buscar)  { 
      
        console.log(!isNaN (buscar)) //comprobando que funcione con la funcion isNan

      //si lo que recibe del input es un numero
      if(!isNaN (buscar) === true) {
        //busca al personaje por su id
        axios.get('/api/getPersonasUxd.php?id='+buscar).then((response) => {this.buscados = response.data; console.log(this.buscados)
        })
        //si es por ir para que muestre
        this.mostrarBuscadoID = true
        //mantenemos en falso para que no muestre datos de la tarjeta de todos los personajes
        this.mostrarBuscados = false
      }

        
        
    },
  },
}
  function alertar(texto) {
       alert(texto);
    }
</script>

<template >
  <div class="flex justify-center items-center space-x-4 text-base my-2">
    <input class="h-12 wl-5 px-7" type="text" v-model="buscar" placeholder="Ingrese ID ">
    <button @click="buscador(buscar)" type="button"
      class="inline-block rounded-full bg-neutral-800 px-6 pt-2.5 pb-2 text-xs font-medium uppercase leading-normal text-neutral-50 shadow-[0_4px_9px_-4px_#332d2d] transition duration-150 ease-in-out hover:bg-neutral-800 hover:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] focus:bg-neutral-800 focus:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] focus:outline-none focus:ring-0 active:bg-neutral-900 active:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.3),0_4px_18px_0_rgba(51,45,45,0.2)] dark:bg-neutral-900 dark:shadow-[0_4px_9px_-4px_#171717] dark:hover:bg-neutral-900 dark:hover:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)] dark:focus:bg-neutral-900 dark:focus:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)] dark:active:bg-neutral-900 dark:active:shadow-[0_8px_9px_-4px_rgba(27,27,27,0.3),0_4px_18px_0_rgba(27,27,27,0.2)]"> Buscar </button>
  </div>
  <br>
  <br>

  <div >
      <div>
        <div >
          <ul class="grid grid-cols-2" >
            <li v-for="p in buscados" class="bg-green-500 p-4 sm:p-6 lg:p-8">
              <center>
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <img src="https://cdn.icon-icons.com/icons2/1378/PNG/512/avatardefault_92824.png" width="300" height="300">
                  <br>
                  <p class="text-xl font-bold text-black sm:text-2xl">{{p.nombre}}</p>
                  <br>
                </div>
              </center>
            </li>
            <li v-for="p in buscados" class="bg-green-500 p-4 sm:p-6 lg:p-8">
              <center>
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <p class="text-xl font-bold text-white sm:text-2xl">Mis personalidades</p>
                  <br>
                  <div class="w-full mt-4">
                    <label class="block text-black font-bold md:text-left my-2 md:mb-0">
                      Personalidad 1 "Mente"  
                    </label>
                    <div class="flex justify-between px-3  ">
                      <label class="text-black  text-left md:text-left my-2 md:mb-0">
                        Extrovertido: {{ p.personalidad01 }}%
                      </label>
                            
                      <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
                        Introvertido: {{ 100 - p.personalidad01 }}%
                      </label>
                    </div>
                    <input type="range" min="0" max="100" v-model="p.personalidad01" class="w-full px-3 rounded-lg bg-gray-100 focus:shadow focus:bg-white focus:outline-none" disabled>
                  </div>
                  <div class="w-full mt-4">
                    <label class="block text-black font-bold md:text-left my-2 md:mb-0">
                      Personalidad 2 "Energía" 
                    </label>
                    <div class="flex justify-between px-3  ">
                      <label class="text-black  text-left md:text-left my-2 md:mb-0">
                        Intuitivo: {{ p.personalidad02 }}%
                      </label>
                            
                      <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
                        Observador: {{ 100 - p.personalidad02 }}%
                      </label>
                    </div>
                    <input type="range" min="0" max="100" v-model="p.personalidad02" class="w-full px-3 rounded-lg bg-gray-100 focus:shadow focus:bg-white focus:outline-none" disabled>
                  </div>
                  <div class="w-full mt-4">
                    <label class="block text-black font-bold md:text-left my-2 md:mb-0">
                      Personalidad 3 "Naturaleza"  
                    </label>
                    <div class="flex justify-between px-3  ">
                      <label class="text-black  text-left md:text-left my-2 md:mb-0">
                        Pensamientos: {{ p.personalidad03 }}%
                      </label>
                            
                      <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
                        Emocional: {{ 100 - p.personalidad03 }}%
                      </label>
                    </div>
                    <input type="range" min="0" max="100" v-model="p.personalidad03" class="w-full px-3 rounded-lg bg-gray-100 focus:shadow focus:bg-white focus:outline-none" disabled>
                  </div>
                  <div class="w-full mt-4">
                    <label class="block text-black font-bold md:text-left my-2 md:mb-0">
                      Personalidad 4 "Identidad"  
                    </label>
                    <div class="flex justify-between px-3  ">
                      <label class="text-black  text-left md:text-left my-2 md:mb-0">
                        Acertivo: {{ p.personalidad04 }}%
                      </label>
                            
                      <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
                        Cauteloso: {{ 100 - p.personalidad04 }}%
                      </label>
                    </div>
                    <input type="range" min="0" max="100" v-model="p.personalidad04" class="w-full px-3 rounded-lg bg-gray-100 focus:shadow focus:bg-white focus:outline-none" disabled>
                  </div>
                </div>
              </center>
            </li>
            <li v-for="p in buscados" class="bg-green-500 p-4 sm:p-6 lg:p-8">
              
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <center>
                    <p class="text-xl font-bold text-white sm:text-2xl">Información Personal</p>        
                  </center>
            
                  <br>
                  <p class="text-xl font-bold text-black sm:lg">Edad: {{p.edad}}</p>
                  <br>
                  <p class="text-xl font-bold text-black sm:lg">Estado civil: {{p.estadoCivil}}</p>
                  <br>
                  <p class="text-xl font-bold text-black sm:lg">Residencia: {{p.residencia}}</p>
                  <br>
                  <p class="text-xl font-bold text-black sm:lg">Trabajo: {{p.trabajo}}</p>
                  <br>
                  <p class="text-xl font-bold text-black sm:lg">Marcas:</p>
                  <li v-for="q in p.marcas" class="bg-green-500 p-4 sm:p-6 lg:p-8">
                      <p class="text-xl font-bold text-black sm:text-lg">Marca {{q.id}}:</p>
                      <p class="text-xl font-bold text-black sm:text-base">- {{q.marca}}</p>
                  </li>
                  <br>
                  <p class="text-xl font-bold text-black sm:lg italic ...">Cita: "{{p.cita}}" - {{p.citaAutor}}</p>
                </div>


            </li>
            <li v-for="p in buscados" class="bg-green-500 p-4 sm:p-6 lg:p-8">
              
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <center>
                    <p class="text-xl font-bold text-white sm:text-2xl">Biografia</p>        
                  </center>
            
                  <br>
                  <p class="text-xl font-bold text-black sm:text-lg">{{p.bio}}</p>
                </div>
              
            </li>
            <li v-for="p in buscados" class="bg-green-500 p-4 sm:p-6 lg:p-8">
              
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <center>
                    <p class="text-xl font-bold text-white sm:text-2xl">Objetivos</p>        
                  </center>
            
                  <li v-for="q in p.objetivos" class="bg-green-500 p-4 sm:p-6 lg:p-8">
                      <div class="relative p-4 sm:p-6 lg:p-8">
                        <p class="text-xl font-bold text-black sm:text-2xl">Objetivo {{q.id}}:</p>
                        <p class="text-xl font-bold text-black sm:text-lg">- {{q.objetivo}}</p>
                      </div>
                    
                  </li>
                </div>
              
            </li>
            <li v-for="p in buscados" class="bg-green-500 p-4 sm:p-6 lg:p-8">
              
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <center>
                    <p class="text-xl font-bold text-white sm:text-2xl">Motivaciones y frustaciones</p>        
                  </center>
            
                  <br>
                  <p class="text-xl font-bold text-white sm:text-2xl">Motivaciones</p>
                  
                  <li v-for="q in p.motivaciones" class="bg-green-500 p-4 sm:p-6 lg:p-8">
                        <p class="text-xl font-bold text-black sm:text-2xl">Motivación {{q.id}}:</p>
                        <p class="text-xl font-bold text-black sm:text-lg">- {{q.motivacion}}</p>
                        <input type="range" min="0" max="100" v-model="q.porcentaje" class="w-full px-3 rounded-lg bg-gray-100 focus:shadow focus:bg-white focus:outline-none" disabled>
                        Porcentaje: {{ q.porcentaje }}%
                    
                  </li>

                  <p class="text-xl font-bold text-white sm:text-2xl">Frustraciones</p>
                  <li v-for="r in p.frustraciones" class="bg-green-500 p-4 sm:p-6 lg:p-8">
                      <p class="text-xl font-bold text-black sm:text-2xl">Frustración {{r.id}}:</p>
                      <p class="text-xl font-bold text-black sm:text-lg">- {{r.frustracion}}</p>
                  </li>

                </div>
              
            </li>
          </ul>
        </div>
      </div>
    </div>
    
    <br>
    <center>
      <div>
        <br>
        <p class="text-xl font-bold text-black text-[48px] align">Usuarios</p>
        <br>
      </div>
    </center>
    <br>

    <div >
      <div>
        <div >
          <ul class="grid grid-cols-5 gap-9" >
            <li v-for="p in personas" class="block rounded-xl border border-black-800 bg-gray-800 p-4 shadow-xl sm:p-6 lg:p-8">
              <center>
                <div class="relative p-4 sm:p-6 lg:p-8">
                  <img src="https://cdn.icon-icons.com/icons2/1378/PNG/512/avatardefault_92824.png" width="300" height="300">

                  <p class="text-xl font-bold text-white sm:text-2xl">ID: {{p.id}}</p>
                  <p class="text-xl font-bold text-white sm:text-lg">{{p.nombre}}</p>
                  <p class="text-xl font-bold text-white sm:text-base">{{p.trabajo}}</p>

                  <br>
                </div>
                </center>
            </li>
          </ul>
        </div>
      </div>
    </div>
</template>