<script>
export default {
    

    props: {
        Datos: String
    },
    
}
</script>

<template>
    <div>
        <slot ></slot> 
        
        <label class="block text-black font-bold md:text-right mb-1 md:mb-0 pr-4" for="inline-full-name">
                        {{ Datos }}
        </label>
    </div>
</template>