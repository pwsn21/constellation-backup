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
                
                <div class="p-10 grid gap-10 sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3 p-10 m-10 text-white bg-white border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
                    <div class="border border-gray-300 rounded-lg p-4"><h2 class="text-xl text-center pb-10">Number of Mentees in progress</h2><div class="text-9xl text-center">10</div></div>
                    <div class="border border-gray-300 rounded-lg p-4"><h2 class="text-xl text-center pb-10">Mentees on Car today</h2>
                            <div v-for="employee in employees.results" class="text-xl py-1">
                                {{ employee.name.first }} {{ employee.name.last }}
                            </div>
                    </div>
                    <div class="text-3xl border border-gray-300 rounded-lg p-4">Some text in here</div>
                    <div class="text-3xl border border-gray-300 rounded-lg p-4">Some text in here</div>
                                       
                </div>



                <!-- <div v-for="employee in employees.results">
                    {{ emp.name.first }}  {{ emp.name.last }}
                    {{ emp.gender }}
                </div> -->
            </div>
        
        
        </div>
    
    </div>
         
    </div>  
</template>

<script setup>
 //    definePageMeta({
   //      layout: 'acpo'
//     })

    const {data:employees}  = await useFetch('https://randomuser.me/api/?results=5')

</script>

<style scoped>

</style>