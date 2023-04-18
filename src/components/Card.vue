<script setup>
    import Inicio from '@/components/Inicio.vue'
    import Footer from '@/components/Footer.vue'
    

    defineProps({
    Numero: {
        type: Object,
        required: true
    },
    Paginas: {
        type: String,
        required: true
    }
    })
</script>



<template >
    <div  class="grid grid-cols-6 gap-4">
        <div class="col-start-2 col-span-4 ...">
        <div class="max-w-sm w-full lg:max-w-full lg:flex p-10 ">

            <div class=" bg-lime-400 rounded-3xl overflow-hidden shadow-xl rounded-b  lg:rounded-xl p-4 flex flex-col justify-between leading-normal">
            <div class="mb-8 grid grid-cols-2">
                <Inicio></Inicio>
            </div>
            
            </div>
        </div>
        
        </div>
        
    </div>

    <Footer></Footer>


</template>

