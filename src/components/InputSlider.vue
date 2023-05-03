<script>
export default {
    
    data() {
        return {
            slider: 50
        }
    },
    props: {
    Datos: String
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
        <slot ></slot> 
        
        ({{ slider }}%)
        <br>
        <p class="text-center p-4 font-bold" >{{ Datos }}</p>
        <input type="range" min="0" max="100" v-model="slider" @change="enviar" class=" appearance-none border-2 border-gray-200 rounded w-full  text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-green-500">
        
    </div>
</template>