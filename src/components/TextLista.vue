<script>
export default {
    
    data() {
        return {
            textarea: '',
        }
    },
    props:{recibido:null},
    methods: {
        enviar() {

            this.$emit('datosTextA',this.textarea,this.recibido)
        }
    }
}
</script>


<template>
    <div>
        <textarea type="text" v-model="textarea" name="dato" id="dato" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" @input="enviar" >
        </textarea>

    </div>
</template>