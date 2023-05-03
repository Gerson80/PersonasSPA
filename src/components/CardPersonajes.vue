<script >
    import Personajes from '@/components/Personajes.vue'
    import Modal from '@/components/Modal.vue'
    import informacion from '@/components/Modal.vue'
    import axios from 'axios'

    export default {
    name: 'app',
    components: {
    Modal,
    },
    props: {
    Datos: Object
  },
    
    data () {
    return {
    isModalVisible: false,
    personaje: [],
    API_URL: ""
    
    };
    },

    methods: {
    showModal() {

        this.isModalVisible = true;
    
    
            

    },
    closeModal() {
    this.isModalVisible = false;
    },
    
    },


    
    };
    
    
    





    
</script>

<template>

        <div class="max-w-sm w-full h-full lg:max-w-full lg:flex p-10 ">

            <button type="button"  @click="showModal"  class=" w-full btn hover:bg-green-500  bg-lime-400 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal">
                <div class="">
                    
                    
                    <div class="">
                        <h1 class=" font-bold text-2xl mb-2 text-center">{{ Datos.nombre.toUpperCase() }}</h1>
                    </div>

                    <div class="h-28">
                        <h1 class="  text-lg mb-2">{{ Datos.cita }}</h1>
                    </div>
                    
                </div>
            
            </button>
            
    
            
        </div>

        <div id="app">
            <modal v-show="isModalVisible" @close="closeModal" :DatosModal="Datos"  />

        </div>


        


</template>

