<script>
export default {
    
    data() {
        return {
            input: '',
        }
    },
    methods: {
        enviar() {
            input: this.dato,
            this.$emit('datosInput',this.input)
        }
    }
}
</script>


<template>
    <div>
        <slot></slot> 
        <input type="text" v-model="input" name="dato" id="dato" class="appearance-none block w-full bg-gray-200 text-gray-700 border border-red-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" @input="enviar" >

    </div>
</template>