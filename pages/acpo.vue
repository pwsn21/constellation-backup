<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navbar />
        
        
        <div class="flex-1 md:ml-60 md:mt-0 mt-6">
            <!-- acponav -->
            <!-- <subnavacpo /> -->
            
            <!-- content -->
            <div class="text-blue-100 m-10">
                
                <h2 class="pt-10 text-4xl font-semibold text-center">ACP-Orientation</h2>

                <hr class="my-9 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                
                <div class="grid gap-10 md:grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 text-blue-100 rounded-lg dark:bg-gray-800 dark:border-gray-700">
                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">
                        <h2 class="text-2xl font-semibold text-center pb-3">Number of Mentees in progress</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                    </div>

                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">
                        <h2 class="text-2xl font-semibold text-center pb-3">Mentees on Car today</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                            <div v-for="menteecartoday in menteecartoday.results" class="py-1">
                                {{ menteecartoday.name.first }} {{ menteecartoday.name.last }}
                            </div>
                    </div>
                    
                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">
                        <h2 class="text-2xl font-semibold text-center pb-3">Mentees In Progress - 10</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                            <div v-for="acponame in acpoinprogress.results" class="text-base py-1">
                                {{ acponame.name.first }} {{ acponame.name.last }}
                            </div>
                    </div>

                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">Some text in here</div>

                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">Some text in here</div>
                                       
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

    const {data:menteecartoday}  = await useFetch('https://randomuser.me/api/?results=5')
    const {data:acpoinprogress}  = await useFetch('https://randomuser.me/api/?page=3&results=10&seed=abc')


</script>

<style scoped>

</style>