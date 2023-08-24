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
                
                <h2 class="p-2">Employee Dashboard</h2>

                <div class="pl-10 pt-10">
                    <form class="flex items-center">   
                    <label for="simple-search" class="sr-only">Search</label>
                    <div class="relative">
                        <input type="text" id="simple-search" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5  dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Search Employees" required>
                    </div>
                    </form>
                </div>


                <div class="relative overflow-x-auto  p-10">
                    <table class="relative w-full text-sm text-left text-gray-500 dark:text-gray-400 shadow-md sm:rounded-lg">
                        <thead class="text-xs text-gray-700 uppercase bg-gray-50 dark:bg-gray-700 dark:text-gray-400">
                            <tr>
                                <th scope="col" class="px-6 py-3">
                                    Employee Number
                                </th>
                                <th scope="col" class="px-6 py-3">
                                    Employee Name
                                </th>
                                <th scope="col" class="px-6 py-3">
                                    Email
                                </th>
                                <th scope="col" class="px-6 py-3">
                                    Region
                                </th>
                                <th scope="col" class="px-6 py-3">
                                    Edit
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="employee in employee.results" class="bg-white border-b dark:bg-gray-900 dark:border-gray-700">
                                <th scope="row" class="px-6 py-4 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                                    <NuxtLink to="/profile">{{  employee.location.street.number }}</NuxtLink>
                                </th>
                                <td class="px-6 py-4  bg-gray-50 dark:bg-gray-800">
                                    {{ employee.name.first }} {{ employee.name.last }}
                                </td>
                                <td class="px-6 py-4">
                                    {{ employee.email }}
                                </td>
                                <td class="px-6 py-4  bg-gray-50 dark:bg-gray-800">
                                    {{ employee.dob.age }}
                                </td>
                                <td class="px-6 py-4">
                                    <NuxtLink to="profileedit" class="font-medium text-blue-600 dark:text-blue-500 hover:underline">Edit</NuxtLink>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
            </div>
        
        
        </div>
    
    </div>
         
    </div>  
</template>

<script setup>
//import { NuxtLink } from '.nuxt/components';

 //    definePageMeta({
   //      layout: 'acpo'
//     })

    const { data: employee } = await useFetch('https://randomuser.me/api/?results=9')
</script>

<style scoped>
h2 {
  color: beige;
}

div {
    color:bisque
}

</style>