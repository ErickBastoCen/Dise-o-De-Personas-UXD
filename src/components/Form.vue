<script>
  import axios from 'axios'
  import btnEnviar from '../components/BotonAceptar.vue';
  import slider from '../components/InputSlider.vue';
  import Input from '../components/Input.vue';
  import TextArea from '../components/TextArea.vue';
  import Select from '../components/Select.vue';

  export default {

    components:{
            btnEnviar, slider, Input, TextArea, Select,
        },

    emits: ['person', 'datosInput', 'datosText', 'datosSelect',],
    
    data(){
      return{
        nombre: "",
        edad: "",
        estadoCivil:'',
        trabajo: "",
        residencia: "",
        cita: "",
        citaAutor: "",
        bio: "",
        personalidad01:50,
        personalidad02:50,
        personalidad03:50,
        personalidad04:50,
        marcas: "",
        objetivos: [{value: 'obj1'},{value: 'obj1'},{value: 'obj1'},{value: 'obj1'}],
        frustraciones: [{value: 'obj1'},{value: 'obj1'},{value: 'obj1'},{value: 'obj1'}],
        motivaciones: [{value: 'motivacion','porcentaje':'80'},{value: 'motivacion','porcentaje':'80'},{value: 'motivacion','porcentaje':'80'}]
        

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
            //marca: this.marca
            objetivos:this.objetivos,
            personalidad01: this.personalidad01,
            personalidad02: this.personalidad02,
            personalidad03: this.personalidad03,
            personalidad04: this.personalidad04,
            marcas: this.marcas,
            frustraciones: this.frustraciones,
            motivaciones: this.motivaciones

          }).then((response) => {console.log(response.status)});
        },


        pers1(s){
                this.personalidad01=s;
                console.log(s);
        },
        pers2(s){
                this.personalidad02=s;
                console.log(s);
        },
        pers3(s){
                this.personalidad03=s;
                console.log(s);
        },
        pers4(s){
                this.personalidad04=s;
                console.log(s);
        },


        Nombre(s){
                this.nombre = s;
                console.log(this.nombre);
        },
        Edad(s){
                this.edad = s;
                console.log(this.edad);
        },
        Trabajo(s){
                this.trabajo = s;
                console.log(this.trabajo);
        },
        Residencia(s){
                this.residencia = s;
                console.log(this.residencia);
        },
        Cita(s){
                this.cita = s;
                console.log(this.cita);
        },
        CitaAutor(s){
                this.citaAutor = s;
                console.log(this.citaAutor);
        },
        Bio(s){
                this.bio = s;
                console.log(this.bio);
        },
        Marcas(s){
                this.marcas = s;
                console.log(this.marcas);
        },

        EstadoCivil(s){
                this.estadoCivil = s;
                console.log(this.estadoCivil);
        },
        Motivaciones(s){
                this.motivaciones = s;
                console.log(this.motivaciones);
        },

        soloLetras(e){
        console.log(e)
        },

        Validar(){
          //nombre
          if(this.nombre != "" && !isNaN (this.nombre) === false && this.nombre.length <201 && this.nombre.length > 2 ) {
            console.log("el nombre es correcto")
             
            //edad
            if (this.edad.length < 3 && this.edad != ""){
              console.log("edad existe")
            }else{
              console.log("no existe esa edad")
            }
            //Estado civil
            if (this.estadoCivil != ""){
              console.log("si selecciono estado civil")
            }else{
              console.log("no selecciono estado civil")
              return false
            }
            //Trabajo
            if (this.trabajo.length < 201 && this.trabajo != "" && !isNaN (this.trabajo) === false){
              console.log("trabajo existe")
            }else{
              console.log("no existe trabajo")
              return false
            }
            //Residencia
            if (this.residencia.length < 201 && this.residencia != "" && !isNaN (this.residencia) === false){
              console.log("residencia existe")
            }else{
              console.log("no existe residencia")
              return false
            }
            //Cita
            if (this.cita.length < 501 && this.cita != "" && !isNaN (this.cita) === false){
              console.log("Cita existe")
            }else{
              console.log("Cita no existe")
              return false
            }
            //CitaAutor
            if (this.citaAutor.length < 501 && this.citaAutor != "" && !isNaN (this.citaAutor) === false){
              console.log("CitaAutor existe")
            }else{
              console.log("CitaAutor no existe")
              return false
            }
            //Bio
            if (this.bio.length < 701 && this.bio != "" && !isNaN (this.bio) === false){
              console.log("Bio correcta")
            }else{
              console.log("Bio incorrecta")
              return false
            }
          return true
                       
          }
          else{
            console.log("No pude registrarlo")
            return false
          }
        }
      }
    }
    function Mostrar(){
      alert("Usuario Registrado")
    }
</script>

<template>
  <center>
    <br>
    <center>
      <div>
        <br>
        <p class="text-xl font-bold text-black text-[48px] align">Registrate con nosotros</p>
        <br>
      </div>
    </center>
    <br>

    <img src="https://cdn.icon-icons.com/icons2/1378/PNG/512/avatardefault_92824.png" width="300" height="300">
    <br>
    <br>
    <form class="w-full max-w-lg">
      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Nombres
          </label>
          <Input @datosInput="Nombre" @input="soloLetras" ></Input>
          <p class="text-red-500 text-xs italic">Por favor introduzca su nombre.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Edad
          </label>
          <Input @datosInput="Edad" @input="soloLetras" ></Input>
          <p class="text-red-500 text-xs italic">Por favor introduzca su edad.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
              Estado Civil
          </label>
          <div class="relative">
            <Select @datosSelect="EstadoCivil" @input="soloLetras"></Select>
          </div>
          <p class="text-gray-600 text-xs italic">Introduzca su estado civil.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Trabajo
          </label>
          <Input @datosInput="Trabajo" @input="soloLetras" ></Input>
          <p class="text-red-500 text-xs italic">Por favor introduzca su trabajo.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Residencia
          </label>
          <Input @datosInput="Residencia" @input="soloLetras" ></Input>
          <p class="text-red-500 text-xs italic">Por favor introduzca el lugar de residencia.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Cita
          </label>
          <TextArea @datosText="Cita" @input="soloLetras" ></TextArea> 
          <p class="text-red-500 text-xs italic">Por favor introduzca su cita.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Autor de la cita
          </label>
          <Input @datosInput="CitaAutor" @input="soloLetras" ></Input>
          <p class="text-red-500 text-xs italic">Por favor introduzca el autor de su cita.</p>
        </div>
      </div>

      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Biografía
          </label>
          <TextArea @datosText="Bio" @input="soloLetras" ></TextArea> 
          <p class="text-red-500 text-xs italic">Por favor introduzca su biografía.</p>
        </div>
      </div>

      <br>
      
        <h1 class="text-2xl  text-center font-bold  text-black">Mis personalidades</h1>
        <div class="w-full mt-4">
          <label class="block text-black font-bold md:text-left my-2 md:mb-0">
            Personalidad 1 "Mente"  
          </label>
          <div class="flex justify-between px-3  ">
            <label class="text-black  text-left md:text-left my-2 md:mb-0">
              Extrovertido: {{ this.personalidad01 }}%
            </label>
                  
            <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
              Introvertido: {{ 100 - this.personalidad01 }}%
            </label>
          </div>
          <slider @person="pers1"></slider>
        </div>
        <div class="w-full mt-4">
          <label class="block text-black font-bold md:text-left my-2 md:mb-0">
            Personalidad 2 "Energía" 
          </label>
          <div class="flex justify-between px-3  ">
            <label class="text-black  text-left md:text-left my-2 md:mb-0">
              Intuitivo: {{ this.personalidad02 }}%
            </label>
                  
            <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
              Observador: {{ 100 - this.personalidad02 }}%
            </label>
          </div>
          <slider @person="pers2"></slider>
        </div>
        <div class="w-full mt-4">
          <label class="block text-black font-bold md:text-left my-2 md:mb-0">
            Personalidad 3 "Naturaleza"  
          </label>
          <div class="flex justify-between px-3  ">
            <label class="text-black  text-left md:text-left my-2 md:mb-0">
              Pensamientos: {{ this.personalidad03 }}%
            </label>
                  
            <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
              Emocional: {{ 100 - this.personalidad03 }}%
            </label>
          </div>
          <slider @person="pers3"></slider>
        </div>
        <div class="w-full mt-4">
          <label class="block text-black font-bold md:text-left my-2 md:mb-0">
            Personalidad 4 "Identidad"  
          </label>
          <div class="flex justify-between px-3  ">
            <label class="text-black  text-left md:text-left my-2 md:mb-0">
              Acertivo: {{ this.personalidad04 }}%
            </label>
                  
            <label class="text-black  text-end  mr-0 md:text-right my-2 md:mb-0">
              Cauteloso: {{ 100 - this.personalidad04 }}%
            </label>
          </div>
          <slider @person="pers4"></slider>
        </div>
      
      <br>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Marca
          </label>
          <Input @datosInput="Marcas" @input="soloLetras" ></Input>
          <p class="text-red-500 text-xs italic">Por favor introduzca el autor de su marca.</p>
        </div>
      </div>


      <div class="flex flex-wrap -mx-3 mb-6">
        <div class="w-full px-3">
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" >
            Objetivos
          </label>
          <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="objetivos" type="text" placeholder="El diseño no es solo lo que parece y se siente..." v-model="objetivos" >

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
          <TextArea @datosText="Motivaciones" @input="soloLetras" ></TextArea> 
          <p class="text-red-500 text-xs italic">Por favor introduzca sus motivaciones.</p>
        </div>
      </div>
    </form>


    <btnEnviar @click="submit()" onclick="alert('Usuario Registrado')" v-if=" nombre != '' && marcas != ''">Registrar persona</btnEnviar>
    
  </center>
</template>
