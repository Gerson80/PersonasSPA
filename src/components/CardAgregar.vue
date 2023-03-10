<script>
import btnEnviar from '../components/btnSubmit.vue';
import slider from '../components/InputSlider.vue';
import Titulo from '../components/Label.vue';
import Seleccion from '../components/Select.vue';

import axios from 'axios'





export default {
    components:{
            btnEnviar,slider,Titulo,Seleccion
        },
    emits: ['valor'],
    data() {
        return {
            Nombre: " ",
            Edad: " ",
            EstadoCivil: " ",
            Trabajo:" ",
            Residencia: " ",
            Cita: " ",
            CitaAutor: " ",
            Bio: " ",
            Personalidad1: " ",
            Personalidad2:" ",
            Personalidad3: " ",
            Personalidad4: " ",
            Objetivos: " ",
            Frustraciones: [],
            Motivaciones: [],
            Marcas: " "






        };
    },
    mounted() {
        

    },
    methods: {
        Enviar(){

            

            axios.post("/api/guardarPersonasUxd.php", {
                nombre: this.Nombre,
                edad: this.Edad,
                estadoCivil: this.EstadoCivil,
                trabajo: this.Trabajo,
                residencia: this.Residencia,
                cita: this.Cita,
                citaAutor: this.CitaAutor,
                bio: this.Bio,
                personalidad01: this.Personalidad1,
                personalidad02: this.Personalidad2,
                personalidad03: this.Personalidad3,
                personalidad04: this.Personalidad4,
                objetivos: this.Objetivos,
                frustraciones: this.Frustraciones,
                motivaciones: this.Motivaciones,
                marcas: this.Marcas




                //completar las variables, estas deben llamarse como las que se recibirán en el backend sin el símbolo del dolar $
            })
            .then((response) => {
            console.log(response.status)
            });


        },
        guardarLocal(){
                localStorage.setItem('nombreCompleto', this.nombreCompleto);
            },
            recuperarLocal(){
                this.nombreCompleto=localStorage.getItem('nombreCompleto');
            },
            pers1(s){
                this.pers01=s;
                console.log(s);
            },
            pers2(s){
                this.pers02=s;
                console.log(s);
            },

            sele(s){
                
                console.log(s);
            }


    }
}


</script>




<template >
    <div class="flex justify-center">
        <div class="block max-w-sm rounded-lg p-6 shadow-lg bg-sky-500 ">
            <div class="text-center p-2 font-bold text-xl" >
                <h1>Personalidad</h1>
            </div>
            <form class="w-full max-w-sm" method="get">
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                    
                    <Titulo Datos="Nombre" />
                    
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Nombre" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Edad" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Edad" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Estado civil" />
                    </div>
                    <div class="md:w-2/3">
                       
                       <Seleccion @valor="sele" :Datos='{"Uno": "Soltero","Dos": "Casado","Tres": "Divorciado","Cuatro": "Separado","Cinco": "Union libre","Seis": "Viudo"} '     />
                    </div>
                    
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Trabajo" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Trabajo" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Residencia" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Residencia" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Cita" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Cita" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Cita autor" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="CitaAutor" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text">
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Bio" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Bio" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers1" Datos="Personalidad 1">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Personalidad 1</h3>
                        
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers1">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Personalidad 2</h3>
                        
                        </slider>
                    </div>
                </div>

                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers1">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Personalidad 3</h3>
                        
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers1">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Personalidad 4</h3>
                        
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Objetivos" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Objetivos" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Frustraciones" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Objetivos" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Motivaciones" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Objetivos" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Marcas" />
                    </div>
                    <div class="md:w-2/3">
                    <input v-model="Marcas" class="bg-gray-200 appearance-none border-2 border-gray-200 rounded w-full py-2 px-4 text-gray-700 leading-tight focus:outline-none focus:bg-white focus:border-purple-500" id="inline-full-name" type="text" >
                    </div>
                </div>





                
                <div class="md:flex md:items-center">
                    <div class="md:w-1/3"></div>
                    <div class="md:w-2/3">
                        <div @click="Enviar()">
                            <button class="shadow bg-purple-500 hover:bg-purple-400 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
                                Enviar
                            </button>
                        </div>
                    
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>