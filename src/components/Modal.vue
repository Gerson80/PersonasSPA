<script>
    export default {
        name: 'modal',
        methods: {
        close() {
        this.$emit('close');
        },
        },

        props: {
            DatosModal: String
        },
        };
</script>


<template>
    <transition name="modal-fade">
        <div class="modal-backdrop fixed top-0 bottom-0 left-0 right-0 flex justify-center items-center">
            <div class="modal bg-lime-400 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal  w-1/3">
                <div class="mb-2 grid grid-cols-2">
                        <div class="text-sm text-gray-600 flex w-44">
                            <img class="w-44 h-56 rounded-xl mr-4" v-bind:src=  DatosModal.image alt="Avatar of Jonathan Reinink">
                                    
                        </div>
                        <div > 
                            <div class="text-center">
                                <h2 class="text-black  text-lg mb-2 font-bold">{{ DatosModal.name }}</h2>
                            </div>         
                            
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black  text-lg">Estado:</p>
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.status }}</p>
                            </div>
                            
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black  text-lg ">Especie:</p>
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.species }}</p>
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Tipo:</p>   
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.type }}</p>
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Genero:</p>   
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.gender }}</p>
                            </div>
 
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg">Origen:</p>   
                                <p class="text-white  text-lg  col-span-2">{{ DatosModal.origin.name }}</p>
                            </div>
                            <div class="mb-2 grid grid-cols-3">
                                <p class="text-black text-lg ">Locacion:</p>   
                                <p class="text-white  text-lg col-span-2">{{ DatosModal.location.name }}</p>
                            </div>
                        
                        </div>  

                    </div>
                <button
                        type="button"
                        class="btn-green"
                        @click="close"
                        aria-label="Close Modal App"
                        >
                        Cerrar
                        </button>
                
            </div>
        </div>
    </transition>
</template>

