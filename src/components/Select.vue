<script>
export default {
    
    data() {
        return {
            slider: 50,
            value: 0
        }
    },
    props: {
    Datos: Object
    },
    methods: {
        enviar() {
            this.$emit('valor',this.value)
        }
    }
    
}

</script>

<template>
    <div>
        <slot ></slot> 
        
        <select  v-model="value" @change="enviar" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-green-500">
                            <option value="1">{{ Datos.Uno }}</option>
                            <option value="2">{{ Datos.Dos }}</option>
                            <option value="3">{{ Datos.Tres }}</option>
                            <option value="4">{{ Datos.Cuatro }}</option>
                            <option value="5">{{ Datos.Cinco }}</option>
                            <option value="6">{{ Datos.Seis }}</option>
                            

        </select>
    </div>
</template>