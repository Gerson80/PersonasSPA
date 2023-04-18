<script>
    import DatosPersona from '@/components/DatosPersona.vue';



    export default {
        
    name: 'DatosPersona2',
    components: {
    
    },
    props: {
            Dato: Object
    },
    data(){

    },
    methods: {
        close() {
        this.$emit('close');
        
        },
        
        },
        

   
    };
   
</script>

<template>
    
    <div  class="grid grid-cols-6 gap-4">
        <div class="col-start-2 col-span-4 ...">
        <div class="max-w-sm w-full lg:max-w-full lg:flex p-10 ">

            <div class=" bg-lime-400 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal">
            <div class="mb-8 grid grid-cols-2">
                <div class="text-center">
                                <h2 class="text-black  text-lg mb-2 font-bold"></h2>
                            </div>         
                            <p>dfg {{  Dato }}</p>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black  text-lg">Edad:</p>
                                <p class="text-white  text-lg col-span-2"></p>
                            </div>
                            
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black  text-lg ">Estado Civil:</p>
                               
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Trabajo:</p>   
                                <p class="text-white  text-lg col-span-2"></p>
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Residencia:</p>   
                                <p class="text-white  text-lg col-span-2"></p>
                            </div>
 
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg">Cita:</p>   
                                <p class="text-white  text-lg  col-span-2"></p>
                            </div>
                            
            </div>
            
            </div>
        </div>
        </div>
        
    </div>
        

</template>

