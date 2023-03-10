<script>
export default {
    
    data() {
        return {
            slider: 50
        }
    },
    methods: {
        enviar() {
            this.$emit('person',this.slider)
        }
    }
}
</script>

<template>
    <div>
        <br>
        <slot></slot>
        <br>
        <input type="range" min="0" max="100" v-model="slider" class="w-full px-3 rounded-lg bg-gray-100 focus:shadow focus:bg-white focus:outline-none" @change="enviar">
        <br>
    </div>
</template>