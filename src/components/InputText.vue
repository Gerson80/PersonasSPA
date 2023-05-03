<script>
export default {
    
    data() {
        return {
            slider: 50,
            value:''
        }
    },
    props: {
    Datos: Object
    },
    methods: {
        enviar() {
            this.$emit('valorInput',this.value)
        }
    }
    
}

</script>

<template>
    <input v-model="value" @change="enviar" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-green-500" id="inline-full-name" type="text" >
</template>