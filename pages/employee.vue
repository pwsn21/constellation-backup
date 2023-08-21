<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navigate />
        
        
        <div class="flex-1">
            <!-- acponav -->
            <subnavacpo />
            
            <!-- content -->
            <div class="mx-auto font-extrabold text-3xl">
                
                Employee Dashboard

                <div class="grid grid-cols-3 gap-4 font-normal text-base">
                    <div v-for="employee in employee">
                        <div>{{ employee }}</div>
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

    const { data: employee } = await useFetch('https://randomuser.me/api/?results=5')
</script>

<style scoped>

</style>