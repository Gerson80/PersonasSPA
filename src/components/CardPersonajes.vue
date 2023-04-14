<script >
    import Personajes from '@/components/Personajes.vue'
    import Modal from '@/components/Modal.vue'
    import informacion from '@/components/Modal.vue'

    export default {
    name: 'app',
    components: {
    Modal,
    },
    props: {
    Datos: String
  },
    
    data () {
    return {
    isModalVisible: false,
    };
    },
    
    methods: {
    showModal() {
    this.isModalVisible = true;
    CardPersonajes :Datos= p  
    },
    closeModal() {
    this.isModalVisible = false;
    }
    },


    
    };
    
    
    





    
</script>

<template>

        <div class="max-w-sm w-full lg:max-w-full lg:flex p-10 ">

            <button type="button"  @click="showModal" class=" btn hover:bg-green-500  bg-lime-400 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal">
                <div class="">
                    <div class="w-32 h-48 conteiner-md">
                        <img class="w-28 h-48 rounded-xl mr-4" v-bind:src=  Datos.image  alt="Avatar of Jonathan Reinink">
                    </div>
                    
                    <div class="h-28">
                        <h1 class="font-bold text-3xl mb-2 text-center">{{ Datos.name }}</h1>
                    </div>
                    
                </div>
            
            </button>
            
    
            
        </div>

        <div id="app">
            <modal v-show="isModalVisible" @close="closeModal" :DatosModal="Datos"  />

        </div>


        


</template>

