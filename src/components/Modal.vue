<script>
    import DatosPersona from '@/components/DatosPersona.vue';



    export default {
    name: 'DatosPersona',
    components: {
    DatosPersona,
    },
    props: {
            DatosModal: Object
    },
    data(){

    },
    methods: {
        close() {
        this.$emit('close');
        },
        enviarDatos(Dato) {
        this.$router.push({ name: 'dato', params: { Dato }})
        
        }
        },


        
    };
</script>


<template>
    
    <transition name="modal-fade">
        
        <div class="modal-backdrop fixed top-0 bottom-0 left-0 right-0 flex justify-center items-center">
            <div class="modal bg-green-500 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal  w-4/5">
                <div > 
                            <div class="text-center">
                                <h2 class="text-black  text-lg mb-2 font-bold">{{ DatosModal.nombre.toUpperCase() }}</h2>
                            </div>         
                            
                            
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black  text-lg">Edad:</p>
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.edad }}</p>
                            </div>
                            
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black  text-lg ">Estado Civil:</p>
                                <p v-if="DatosModal.estadoCivil=1" class="text-white  text-lg col-span-2">Soltero</p>
                                <p v-else-if="DatosModal.estadoCivil=2" class="text-white  text-lg col-span-2">Casado</p>
                                <p v-else-if="DatosModal.estadoCivil=3" class="text-white  text-lg col-span-2">Divorciado</p>
                                <p v-else-if="DatosModal.estadoCivil=4" class="text-white  text-lg col-span-2">Separado</p>
                                <p v-else-if="DatosModal.estadoCivil=5" class="text-white  text-lg col-span-2">Unión libre</p>
                                <p v-else="DatosModal.estadoCivil=6" class="text-white  text-lg col-span-2">Viudo</p>
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Trabajo:</p>   
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.trabajo }}</p>
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Residencia:</p>   
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.residencia }}</p>
                            </div>
 
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg">Cita:</p>   
                                <p class="text-white  text-lg  col-span-2">{{ DatosModal.cita }}</p>
                            </div>

                        
                        </div>  

                        <div class="text-center">
                            <button  @click="enviarDatos({ nombre: 'Juan', edad: 30 })" class="px-4  hover:bg-lime-500 hover:rounded-xl active:bg-green-500  focus:ring-green-300 ..." >Ver
                            
                           
                                
                                
                            </button>
                           
                            

                      
                            
                        <button
                        type="button"
                        class="px-4  hover:bg-lime-500 hover:rounded-xl active:bg-green-500  focus:ring-green-300 ..."
                        @click="close"
                        aria-label="Close Modal App"
                        >
                        Cerrar
                        </button>

                        </div>
 
                
            </div>
        </div>
    </transition>
   
</template>

