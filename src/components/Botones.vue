<script setup>
    import Personajes from '@/components/Personajes.vue'
    defineProps({
    msg: {
        type: String,
        required: true
    }
    })
</script>

<template>
    
    <button class="px-4 font-sans hover:bg-lime-500 hover:rounded-xl active:bg-green-500  focus:ring-green-300 ...">
        {{ msg }}
        
    </button>

    

</template>