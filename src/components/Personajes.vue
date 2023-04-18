<script>
import axios from 'axios'
import Botones from '@/components/Botones.vue'
import CardPersonajes from './CardPersonajes.vue'


let API_URL = `/api/getPersonasUxd.php`

export default {
    data() {
        return {
            info: [],
            personajes: [],
            cont: 2
        };
    },
    mounted() {
        axios.get(API_URL)
            .then((response) => {
            this.personajes = response.data.personas;
        })

    },
    methods: {
        pag(num) {
            API_URL = "" + num;
            console.log(API_URL);
            axios.get(API_URL)
                .then((response) => {
                console.log(response.config);
                this.info = response.data.info;
                this.personajes = response.data.results;
            });
            this.cont++;
        },
        pag2(num) {
            API_URL = "" + num;
            console.log(API_URL);
            axios.get(API_URL)
                .then((response) => {
                console.log(response.config);
                this.info = response.data.info;
                this.personajes = response.data.results;
            });
            this.cont--;
        },
        
    },
    components: { CardPersonajes, Botones }
    
}


</script>

<template>
  
  <div class="grid gap-4 grid-cols-8 grid-rows-1 py-6">
    <div> </div>
    <div> </div>
    <div> </div>
    <div class="w-96 content-center">
      <label class="relative block">
        <span class="sr-only">Search</span>
        <span class="absolute inset-y-0 left-0 flex items-center pl-2">
          <svg class="h-5 w-5 fill-slate-300" viewBox="0 0 20 20"><!-- ... --></svg>
        </span>
        <input class="placeholder:italic placeholder:text-slate-400 block bg-white w-full border border-slate-300 rounded-md py-2 pl-9 pr-3 shadow-sm focus:outline-none focus:border-green-500 focus:ring-green-500 focus:ring-1 sm:text-sm" placeholder="Buscar..." type="text" name="search"/>
      </label>
  
    </div>
  </div>



  <div class="grid gap-4 grid-cols-8 grid-rows-1 text-center">
    <div> </div>
    <div> </div>
    <div> </div>


    
  </div>

  <div  class="grid grid-cols-3 gap-4 px-10">
    
    
      <div v-for="p in personajes">
        <CardPersonajes :Datos= p  />
       
        
      </div>
   
 
  </div>
  <div class="grid gap-4 grid-cols-8 grid-rows-1 text-center">
    <div> </div>
    <div> </div>
    <div> </div>


    
  </div>



</template>

