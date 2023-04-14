<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import Titulo from './components/Titulo.vue'
import Inicio from './components/Inicio.vue'
import Navegacion from './components/Navegacion.vue'
import Personajes from './components/Personajes.vue'


</script>

<template >
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com" family="Nuevo">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Creepster&display=swap" rel="stylesheet">
  </head>

 

  <header >


    <div>
      <Titulo msg="Rick and Morty" />
      <Navegacion></Navegacion>
      



    </div>
  </header>


  <RouterView />
</template>




