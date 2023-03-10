<script>
export default {
    
    data() {
        return {
            select: '',
        }
    },
    methods: {
        enviar() {
            select: this.dato,
            this.$emit('datosSelect',this.select)
        }
    }
}
</script>


<template>
    <div>
        <slot></slot>
        <select class="block appearance-none w-full bg-gray-200 border border-gray-200 text-gray-700 py-3 px-4 pr-8 rounded leading-tight focus:outline-none focus:bg-white focus:border-gray-500" v-model="select" name="dato" id="dato" @change="enviar">
            <option value="1">Soltero(a)</option>
            <option value="2">Casado(a)</option>
            <option value="3">Divorciado(a)</option>
            <option value="4">Separado(a)</option>
            <option value="5">Unión libre(a)</option>
            <option value="6">Viudo(a)</option>
        </select>

    </div>
</template>