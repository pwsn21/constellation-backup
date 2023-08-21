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
                
                ACP-O Dashboard

                <div>
                //ok going to play locally, give me one sec ...
                
                <!-- still nothing -->
                {{  employees.results[0].name }} 
                    <!--<div v-for="employee in employees">
                        <div>{{ employee.name }}</div>
                   </div>-->
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

    //const { data: employee } = await useFetch('https://randomuser.me/api/?results=5')
    const  employees  = await useFetch('https://randomuser.me/api/?results=5')

</script>

<style scoped>

</style>