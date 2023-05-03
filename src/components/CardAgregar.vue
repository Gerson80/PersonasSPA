<script>
import btnEnviar from '../components/btnSubmit.vue';
import slider from '../components/InputSlider.vue';
import Titulo from '../components/Label.vue';
import Seleccion from '../components/Select.vue';
import InputText from '../components/InputText.vue';

import axios from 'axios'






export default {
    components:{
            btnEnviar,slider,Titulo,Seleccion,InputText
        },
    emits: ['valor', 'valorInput'],
    data() {
        return {
            Nombre: " ",
            Edad:0,
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
            Objetivos: [],
            Objetivos2: [],
            Objetivos3: [],
            Objetivos4: [],
            Frustraciones: [],
            Frustraciones2: [],
            Frustraciones3: [],
            Frustraciones4: [],
            Motivaciones: [],
            Motivaciones2: [],
            Motivaciones3: [],
            Motivaciones4: [],
            Marcas: [],
            Marcas2: ' ',
            Marcas3: ' ',
            Marcas4: ' ',
            Prueba: " ",
            Contador: 1,
            ContadorFrustraciones: 1,
            ContadorMotivaciones: 1,
            ContadorMarcas: 1,
            DatoAgregar: false,
            DatoAgregar2: false,
            DatoAgregarFrustraciones: false,
            DatoAgregar2Frustraciones: false,
            DatoAgregarMotivacion: false,
            DatoAgregar2Motivacion: false,
            DatoAgregarMarcas: false,
            DatoAgregar2Marcas: false,
            ValMotivacion: 0,
            ValMotivacion2: 0,
            ValMotivacion3: 0,
            isModalVisible: true,
            isModalVisible2: true,
            isModalVisible3: true,
            isModalVisible4: true,
            






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
            console.log(this.Objetivos)
            }
            
            
            )
            .catch(error => {
    console.error(error);
    // manejar el error
  });
            


        },
        guardarLocal(){
                localStorage.setItem('nombreCompleto', this.nombreCompleto);
            },
            recuperarLocal(){
                this.nombreCompleto=localStorage.getItem('nombreCompleto');
            },
            pers1(s){
                this.Personalidad1=s;
                console.log(this.Personalidad1);
            },
            pers2(s){
                this.Personalidad2=s;
                console.log(this.Personalidad2);
            },
            pers3(s){
                this.Personalidad3=s;
                console.log(this.Personalidad3);
            },
            pers4(s){
                this.Personalidad4=s;
                console.log(this.Personalidad4);
            },

            sele(s){
                
                console.log(s);
            },

            inputNormal(s){
                
                
                this.Prueba= s
                console.log(this.Prueba);
            },

            metodoSelect(s){
                this.EstadoCivil= s
                console.log(this.EstadoCivil);

            },

            AgregarInput(s){
                this.Contador=this.Contador+s
                if(this.Contador==2){
                    this.DatoAgregar=true
                }
                if(this.Contador==3){
                    this.DatoAgregar2=true
                    this.isModalVisible = false;
                }
            },

            AgregarObjetivos(s){
                this.Objetivos2=s
                this.Objetivos=[{value: s}]
                console.log(this.Objetivos)

            },
            AgregarObjetivos2(s){
                this.Objetivos3=s
                this.Objetivos=[{value: this.Objetivos2},{value: this.Objetivos3}]
                console.log(this.Objetivos3)

            },
            AgregarObjetivos3(s){
                this.Objetivos4=s
                
                this.Objetivos=[{value: this.Objetivos2},{value: this.Objetivos3},{value: this.Objetivos4}]

                console.log(this.Objetivos4)
                console.log(this.Objetivos)
                


            },

            AgregarInput2(s){
                this.ContadorFrustraciones=this.ContadorFrustraciones+s
                if(this.ContadorFrustraciones==2){
                    this.DatoAgregarFrustraciones=true
                }
                if(this.ContadorFrustraciones==3){
                    this.isModalVisible2 = false;
                    this.DatoAgregar2Frustraciones=true
                }
            },

            AgregarFrustraciones(s){
                this.Frustraciones2=s
                this.Frustraciones=[{value: s}]
                console.log(this.Frustracioness)

            },
            AgregarFrustraciones2(s){
                this.Frustraciones3=s
                this.Frustraciones=[{value: this.Frustraciones2},{value: this.Frustraciones3}]
                console.log(this.Frustraciones3)

            },
            AgregarFrustraciones3(s){
                this.Frustraciones4=s
                this.Frustraciones=[{value: this.Frustraciones2},{value: this.Frustraciones3},{value: this.Frustraciones4}]

                console.log(this.Frustraciones4)
                console.log(this.Frustraciones)


            },

            AgregarInput3(s){
                this.ContadorMotivaciones=this.ContadorMotivaciones+s
                if(this.ContadorMotivaciones==2){
                    this.DatoAgregarMotivacion=true
                }
                if(this.ContadorMotivaciones==3){
                    this.DatoAgregar2Motivacion=true
                    this.isModalVisible3 = false;
                }
            },
            AgregarMotivaciones(s){
                this.Motivaciones2=s
                this.Motivaciones={value: s,'porcentaje': this.ValMotivacion}
                console.log(this.Motivaciones)

            },
            AgregarMotivaciones2(s){
                this.Motivaciones3=s
                this.Motivaciones=[{value: this.Motivaciones2,'porcentaje': this.ValMotivacion},{value: this.Motivaciones3,'porcentaje':s}]
                console.log(this.Motivaciones3)

            },
            AgregarMotivaciones3(s){
                this.Motivaciones4=s
                this.Motivaciones=[{value: this.Motivaciones2},{value: this.Motivaciones3},{value: this.Motivaciones4}]

                console.log(this.Motivaciones4)
                console.log(this.Motivaciones)


            },

            ValorMotivacion(s){
                this.ValMotivacion=s;
                this.Motivaciones={value: this.Motivaciones2,'porcentaje':s}
                console.log(this.Motivaciones);
            },
            ValorMotivacion2(s){
                this.ValMotivacion2=s;
                this.Motivaciones=[{value: this.Motivaciones2,'porcentaje': this.ValMotivacion},{value: this.Motivaciones3,'porcentaje': this.ValMotivacion2}]
                
                
            },
            ValorMotivacion3(s){
                this.ValMotivacion3=s;
                this.Motivaciones=[{value: this.Motivaciones2,'porcentaje': this.ValMotivacion},{value: this.Motivaciones3,'porcentaje': this.ValMotivacion2},{value: this.Motivaciones4,'porcentaje': this.ValMotivacion3}]
                console.log(this.Motivaciones);
            },

            AgregarInput4(s){
                this.ContadorMarcas=this.ContadorMarcas+s
                if(this.ContadorMarcas==2){
                    this.DatoAgregarMarcas=true
                }
                if(this.ContadorMarcas==3){
                    this.DatoAgregar2Marcas=true
                    this.isModalVisible4 = false;
                }
            },

            AgregarMarcas(s){
                this.Marcas2=s
                this.Marcas=  s
                console.log(this.Marcas)

            },
            AgregarMarcas2(s){
                this.Marcas3= s
                this.Marcas= this.Marcas+','+this.Marcas3
                console.log(this.Marcas3)
                console.log(this.Marcas)

            },
            AgregarMarcas3(s){
                this.Marcas4=s
                this.Marcas= this.Marcas+','+this.Marcas4

                console.log(this.Marcas4)
                console.log(this.Marcas)


            },

    }
}


</script>




<template >
    <div class="">
        <div class="  rounded-lg p-10 shadow-lg  ">
            <div class="text-center p-2 font-bold text-xl" >
                <h1>Personalidad</h1>
            </div>
            <div class=" grid grid-cols-3" >
                <p></p>
                <img src="./per.png" alt="Imagen de ejemplo" width="200" height="200" class="place-self-center" id="mi-imagen">
            </div>
           
            <form class="w-full " method="get">
                <div class="grid grid-cols-3 pr-10 pl-10">
                    <div class="md:flex md:items-center mb-6">
                        <div class="">
                        
                        <Titulo Datos="Nombre" />
                        
                        </div>
                    <div class="md:w-2/3">
                        <InputText  @valorInput="inputNormal" v-model="Nombre"></InputText>
                    </div>


                </div>
                
                
                    <div class="md:flex md:items-center mb-6">
                        <div class="md:w-1/3">
                            <Titulo Datos="Edad" />
                        </div>
                        <div class="md:w-2/3">
                            <InputText  @valorInput="inputNormal" v-model="Edad"></InputText>
                        </div>
                    </div>

                    <div class="md:flex md:items-center mb-6">
                        <div  class="md:w-1/3">
                            <Titulo Datos="Estado civil" />
                        </div>
                        <div class="md:w-2/3">
                        
                        <Seleccion @valor="metodoSelect" :Datos='{"Uno": "Soltero","Dos": "Casado","Tres": "Divorciado","Cuatro": "Separado","Cinco": "Union libre","Seis": "Viudo"} '     />
                        </div>
                    
                    </div>

                </div>

                <div class="grid grid-cols-2 pr-10 pl-10">
                    
                    <div class="md:flex md:items-center mb-6">
                        <div class="md:w-1/3">
                            <Titulo Datos="Trabajo" />
                        </div>
                        <div class="md:w-2/3">
                            <InputText  @valorInput="inputNormal" v-model="Trabajo"></InputText>
                        </div>
                    </div>

                    <div class="md:flex md:items-center mb-6">
                        <div class="md:w-1/3">
                            <Titulo Datos="Residencia" />
                        </div>
                        <div class="md:w-2/3">
                            <InputText  @valorInput="inputNormal" v-model="Residencia"></InputText>
                        </div>
                    </div>

                </div>
                
                
                
                
                <div class="md:flex md:items-center mb-6 pr-10 pl-10">
                    <div class="">
                        <Titulo Datos="Cita" />
                    </div>
                    <div class="w-full">
                        <InputText  @valorInput="inputNormal" v-model="Cita"></InputText>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6 pr-10 pl-10 ">
                    <div class="">
                        <Titulo Datos="Cita autor" />
                    </div>
                    <div class="w-full">
                        <InputText  @valorInput="inputNormal" v-model="CitaAutor"></InputText>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6 pr-10 pl-10">
                    <div class="">
                        <Titulo Datos="Bio" />
                    </div>
                    <div class="w-full">
                        <InputText  @valorInput="inputNormal" v-model="Bio"></InputText>
                        
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers1" Datos="Emprendedor">
                            
                           
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers2" Datos="Relajada">
                            
                            
                        </slider>
                    </div>
                </div>

                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers3" Datos="Detallada" >
                            
                          
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-full">
                        <slider @person="pers4" Datos="Existencialista">
                            
                           
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6"> 
                    <div class="md:w-1/3">
                        <Titulo Datos="Objetivos" />
                        <div >
                            <button v-show="isModalVisible" @click="AgregarInput(1)" class="shadow bg-green-500 hover:bg-green-800 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
                                    Agregar
                            </button>
                        </div>
                    </div>
                    <div class="md:w-2/3 p-4">
                        <InputText  @valorInput="AgregarObjetivos"  ></InputText>
                        
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregar >
                        <InputText  @valorInput="AgregarObjetivos2"  ></InputText>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregar2 >
                        <InputText  @valorInput="AgregarObjetivos3"  ></InputText>
                    </div>
                </div>










                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Frustraciones" />
                        <div >
                            <button v-show="isModalVisible2" @click="AgregarInput2(1)" class="shadow bg-green-500 hover:bg-green-800 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
                                    Agregar
                            </button>
                        </div>
                    </div>
                    <div class="md:w-2/3 p-4">
                        <InputText  @valorInput="AgregarFrustraciones"  ></InputText>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregarFrustraciones >
                        <InputText  @valorInput="AgregarFrustraciones2"  ></InputText>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregar2Frustraciones >
                        <InputText  @valorInput="AgregarFrustraciones3"  ></InputText>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Motivaciones" />
                        <div >
                            <button v-show="isModalVisible3" @click="AgregarInput3(1)" class="shadow bg-green-500 hover:bg-green-800 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
                                    Agregar
                            </button>
                        </div>
                    </div>
                    <div class="md:w-2/3 p-4">
                        <InputText  @valorInput="AgregarMotivaciones"  ></InputText>
                        <slider @person="ValorMotivacion">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Porcentaje</h3>
                        
                        </slider>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregarMotivacion >
                        <InputText  @valorInput="AgregarMotivaciones2"  ></InputText>
                        <slider @person="ValorMotivacion2">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Porcentaje</h3>
                        
                        </slider>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregar2Motivacion >
                        <InputText  @valorInput="AgregarMotivaciones3"  ></InputText>
                        <slider @person="ValorMotivacion3">
                            
                            <h3 class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4">Porcentaje</h3>
                        
                        </slider>
                    </div>
                </div>
                <div class="md:flex md:items-center mb-6">
                    <div class="md:w-1/3">
                        <Titulo Datos="Marcas" />
                        <div >
                            <button v-show="isModalVisible4" @click="AgregarInput4(1)" class="shadow bg-green-500 hover:bg-green-800 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
                                    Agregar
                            </button>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <InputText  @valorInput="AgregarMarcas"  ></InputText>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregarMarcas >
                        <InputText  @valorInput="AgregarMarcas2"  ></InputText>
                    </div>
                    <div class="md:w-2/3 p-4" v-show=this.DatoAgregar2Marcas >
                        <InputText  @valorInput="AgregarMarcas3"  ></InputText>
                    </div>
                </div>





                
                <div class="md:flex md:items-center">
                    <div class="w-full"></div>
                    <div class="w-full">
                        <div @click="Enviar()" class="items-center">
                            <button class="shadow bg-green-500 hover:bg-green-800 focus:shadow-outline focus:outline-none text-white font-bold py-2 px-4 rounded" type="button">
                                Enviar
                            </button>
                        </div>
                    
                    </div>
                </div>
            </form>
        </div>
    </div>
</template>