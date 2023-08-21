<template>
    <div>
    <div class="flex">
        <navigate />
        
        <div class="flex-1">
            <acposubnav />
            
            <div class="mx-auto font-extrabold text-3xl">
                
                ACP-O Dashboard

                <div class="grid grid-cols-3 gap-4 font-normal text-base">
                    <div v-for="p in products">
                        {{ p.title }}
                    </div>
                </div>


            </div>
        
        
        </div>
    
    </div>
         
    </div>  
</template>

<script setup>
 //    definePageMeta({
   //      layout: 'acpo'
//     })

    const { data: products } = await useFetch('https://fakestoreapi.com/products')
</script>

<style scoped>

</style>