<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Titulo from './components/Titulo.vue'
import Inicio from './components/Inicio.vue'
import Navegacion from './components/Navegacion.vue'
import Personajes from './components/Personajes.vue'


</script>

<template >


 

  <header >
 

    <div>
      <Titulo msg="PERSONAS" />
      <Navegacion></Navegacion>
      



    </div>
  </header>

 
    <RouterView />
 
  
</template>


<style>
@import url('https://fonts.googleapis.com/css2?family=Dongle:wght@700&family=Schibsted+Grotesk&display=swap');




*{
  font-family: 'Dongle', sans-serif;
font-family: 'Schibsted Grotesk', sans-serif;

    
  }
</style>



