<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>


<template>
    <div class=" overflow-hidden shadow-lg w-full" name="form1">
        <div class="px-6 py-4 text-white text-xl bg-gradient-to-r from-yellow-300 via-lime-400 to-green-500">
       
            <h1 class="font-bold  text-8xl mb-2 text-center">{{ msg }}</h1>
            
            

        </div>
    </div>
    
    


</template>