<script>
    import axios from 'axios'
    import DatosPersona from '@/components/DatosPersona.vue';


    let API_URL = `/api/getPersonasUxd.php?id=`
    export default {
    name: 'DatosPersona',
    data() {
        return {
            info: [],
            personajes: [],
            personaje: [],
            cont: 2,
            Id: 2,
          
        };
    },
    components: {
    DatosPersona,
    },
    props: {
            DatosModal: Object
    },
    
    mounted() {
        API_URL = "/api/getPersonasUxd.php?id=" + this.DatosModal.id;
            
            axios.get(API_URL)
                .then((response) => {
                this.personaje = response.data.persona;
            });
        

    },

  
    methods: {
        close() {
        this.$emit('close');
        },
        enviarDatos(Dato) {
        this.$router.push({ name: 'dato', params: { Dato }})
        
        },
        Mandado(num) {
            API_URL = "/api/getPersonasUxd.php?id=" + 1;
            console.log(API_URL);
            axios.get(API_URL)
                .then((response) => {
                this.personaje = response.data.persona;
            });
        },
        },


        
    };
</script>


<template>
    
    <transition name="modal-fade">
       
        <div class="modal-backdrop fixed top-0 bottom-0 left-0 right-0 flex justify-center items-center">
            <div class="modal bg-lime-400 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal  w-4/5">
                <div class="pl-10"> 
                            <div class="text-center">
                                <h2 class="text-black  text-lg mb-2 font-bold">{{ DatosModal.nombre.toUpperCase() }}</h2>
                            </div>         
                            <div class="mb-2 grid grid-cols-4">
                                <div class="flex">
                                    <p class="text-black font-bold text-lg">Edad: &nbsp </p>
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.edad }}</p>
                                </div>
                                <div class="flex">
                                    <p class="text-black font-bold text-lg ">Estado Civil: &nbsp</p>
                                    <p v-if="this.personaje.estadoCivil=1" class="text-black  text-lg col-span-2">Soltero</p>
                                    <p v-else-if="this.personaje.estadoCivil=2" class="text-black  text-lg col-span-2">Casado</p>
                                    <p v-else-if="this.personaje.estadoCivil=3" class="text-black  text-lg col-span-2">Divorciado</p>
                                    <p v-else-if="this.personaje.estadoCivil=4" class="text-black  text-lg col-span-2">Separado</p>
                                    <p v-else-if="this.personaje.estadoCivil=5" class="text-black  text-lg col-span-2">Unión libre</p>
                                    <p v-else="this.personaje.estadoCivil=6" class="text-black  text-lg col-span-2">Viudo</p>
                                
                                </div>

                                <div class="flex">
                                    <p class="text-black text-lg font-bold ">Trabajo: &nbsp</p>   
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.trabajo }}</p>
                                </div>

                                <div class="flex">
                                    <p class="text-black text-lg font-bold ">Residencia: &nbsp</p>   
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.residencia }}</p>
                                </div>
                                
                            </div>

                           
                            <div class="text-center">
                                <p class="text-black font-bold text-lg">Cita</p>   
                                <p class="text-black  text-lg  col-span-2">{{ this.personaje.cita }}</p>
                            </div>   
                           
                            <div class="flex">
                                <p class="text-black font-bold text-lg">Autor:&nbsp</p>   
                                <p class="text-black  text-lg  col-span-2">{{ this.personaje.citaAutor }}</p>
                            </div>

                            <div class="text-center">
                                <p class="text-black font-bold text-lg">Biografia</p>   
                                <p class="text-black  text-lg  col-span-2">{{ this.personaje.bio }}</p>
                            </div>   

                            <div class="mb-2 grid grid-cols-4">
                                <div class="flex">
                                    <p class="text-black font-bold  text-lg">Emprendedor:&nbsp </p>
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.personalidad01 }}</p>
                                </div>
                                <div class="flex">
                                    <p class="text-black font-bold  text-lg ">Relajada:&nbsp</p>
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.personalidad02 }}</p>
                                
                                </div>

                                <div class="flex">
                                    <p class="text-black font-bold text-lg ">Detallada:&nbsp</p>   
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.personalidad03 }}</p>
                                </div>

                                <div class="flex">
                                    <p class="text-black font-bold text-lg ">Existencialista:&nbsp</p>   
                                    <p class="text-black  text-lg col-span-2">{{ this.personaje.personalidad04 }}</p>
                                </div>
                                    
                            
                                
                            </div>
                            <div  class="flex">
                                <p  class="text-black font-bold text-lg ">Marcas:&nbsp</p> 
                                <div v-for="m in this.personaje.marcas">
                                    <p class="text-black  text-lg">{{ m.marca+". &nbsp" }}</p>
                                    
                                </div>
                                
                            </div>
                            <div  class="flex">
                                <p  class="text-black font-bold text-lg ">Objetivos:&nbsp</p> 
                                <div v-for="m in this.personaje.objetivos">
                                    <p class="text-black  text-lg">{{ m.objetivo+". &nbsp" }}</p>
                                    
                                </div>
                                
                            </div>
                            <div  class="flex">
                                <p  class="text-black font-bold text-lg ">Frustraciones:&nbsp</p> 
                                <div v-for="m in this.personaje.frustraciones">
                                    <p class="text-black  text-lg">{{ m.frustracion+". &nbsp" }}</p>
                                    
                                </div>
                                
                            </div>
                            <div  class="flex">
                                <p  class="text-black  font-bold text-lg ">Motivaciones:&nbsp</p> 
                                <div v-for="m in this.personaje.motivaciones">
                                    <p class="text-black  text-lg">{{ m.motivacion+". &nbsp" }}</p>
                                    <p class="text-black  text-lg">{{ m.porcentaje+"% &nbsp" }}</p>
                                    
                                </div>
                                
                            </div>

                        
                        </div>  

                        <div class="text-center">
                                
                                

                           
                            

                      
                            
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

