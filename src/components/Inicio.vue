

<script>
import Card from '../components/Card.vue'
import axios from 'axios'


let API_URL = `http://isclab.com.mx/personasuxd/getPersonasUxd.php`

export default {

  data() {
    return {
      info: [],
      cont:2,
      datos:[]
    }
  },

  mounted() {
    axios.get(API_URL)
      .then((response) => {
        this.info = response.data.info;
        this.datos=response.data;
      })
   
      
  },

  methods: {
    pag(num) {
      API_URL='http://isclab.com.mx/personasuxd/getPersonasUxd.php'+num
      console.log(API_URL)
      axios.get(API_URL)
      .then((response) => {
        console.log(response.config)
        this.datos=response.data;
        this.info = response.data.info;
      })
      this.cont++
    },

  },



  components:{
    Card
  }

}

</script>

<template>
  

  

    <div class="text-sm text-gray-600 flex">
      <img class="w-80 h-full rounded-xl mr-4" src="../imagenes/Rick.jpg" alt="Avatar of Jonathan Reinink">
                  
    </div>
    <div >          
      <h2 class="text-black font-bold text-4xl mb-2">Album de "Rick and Morty" de  {{ info.count }} personajes</h2>
      <p class="text-white font-bold text-2xl mb-2">Este albun contiene {{ info.pages }} paginas</p>
      
      <p class="text-black font-bold text-2xl">Sinopsis de la serie</p>
      <p class="text-white text-2xl">Después de haber estado desaparecido durante casi 20 años, Rick Sánchez llega de imprevisto a la puerta de la casa de su hija Beth y se va a vivir con ella y su familia utilizando el garaje como su laboratorio personal.</p>
      <div class="mb-8 grid grid-cols-3">
        <p class="text-black font-bold text-2xl col-span-2">Cantidad de episodios:</p>        
        <p class="text-white font-bold text-2xl">61</p>
      </div>
      <div class="mb-8 grid grid-cols-3">
        <p class="text-black font-bold text-2xl col-span-2">Cantidad de temporadas:</p>
        <p class="text-white font-bold text-2xl">6</p>
      </div>
      <div class="mb-8 grid grid-cols-3">
        <p class="text-black font-bold text-2xl col-span-2">Creadores del programa:</p>   
        <p class="text-white font-bold text-2xl">Justin Roiland, Dan Harmon</p>
      </div>
     
    </div>               
                
  


</template>