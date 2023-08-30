<template>
<div>
    <div class="flex">
        <!-- navbar -->
        <navbar />      
        <div class="flex-1 md:ml-60 md:mt-0 mt-16 justify-center">    
            <div class=" flex justify-center">
                <form @submit.prevent="adddops">
                    <input v-model="dopsskill">
                            <button
                                class="rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]">
                                Add
                            </button>
                </form>
            </div>
            <!-- Add DOPS Button -->
                <NuxtLink to="/adddops/"><button type="button"
                class="ml-10 mb-1 inline-block rounded bg-neutral-800 px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-neutral-50 shadow-[0_4px_9px_-4px_rgba(51,45,45,0.7)] transition duration-150 ease-in-out hover:bg-neutral-800 hover:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.2),0_4px_18px_0_rgba(51,45,45,0.1)] focus:bg-neutral-800 focus:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.2),0_4px_18px_0_rgba(51,45,45,0.1)] focus:outline-none focus:ring-0 active:bg-neutral-900 active:shadow-[0_8px_9px_-4px_rgba(51,45,45,0.2),0_4px_18px_0_rgba(51,45,45,0.1)] dark:bg-neutral-900 dark:shadow-[0_4px_9px_-4px_#030202] dark:hover:bg-neutral-900 dark:hover:shadow-[0_8px_9px_-4px_rgba(3,2,2,0.3),0_4px_18px_0_rgba(3,2,2,0.2)] dark:focus:bg-neutral-900 dark:focus:shadow-[0_8px_9px_-4px_rgba(3,2,2,0.3),0_4px_18px_0_rgba(3,2,2,0.2)] dark:active:bg-neutral-900 dark:active:shadow-[0_8px_9px_-4px_rgba(3,2,2,0.3),0_4px_18px_0_rgba(3,2,2,0.2)]">
                Add DOPS</button></NuxtLink>
            <!-- DOPS Table -->
            <div class="mx-10 rounded-lg shadow-lg">
                <table class="relative w-full text-sm text-left text-gray-500 dark:text-gray-400 shadow-lg">
                    <!-- Table Headers -->
                    <thead class="text-xs uppercase bg-gray-900 text-gray-300 dark:bg-gray-700 dark:text-gray-400">
                        <tr>
                            <th scope="col" class="px-6 py-3">Date</th>
                            <th scope="col" class="px-6 py-3">Mentor</th>
                            <th scope="col" class="px-6 py-3">Car</th>
                            <th scope="col" class="px-6 py-3">Skill</th>
                            <th scope="col" class="px-6 py-3">Edit</th>
                        </tr>
                    </thead>
                    <!-- Table Body -->
                    <tbody>
                        <tr v-for="dops in dopslist2" class="bg-slate-700 border-b border-gray-500 dark:bg-gray-900 dark:border-gray-700">
                            <th scope="row" class="px-6 py-4 font-medium text-black whitespace-nowrap dark:text-white">
                                <NuxtLink to="#">{{ dops.createdon }}</NuxtLink>
                            </th>
                            <td class="px-6 py-4 text-black bg-slate-600 dark:bg-gray-800">{{ dops.mentor }}</td>
                            <td class="px-6 py-4 text-black">{{ dops.car }}</td>
                            <td class="px-6 py-4 text-black bg-slate-600 dark:bg-gray-800">{{ dops.skill }}</td>
                            <td class="px-6 py-4 text-black flex">
                                <NuxtLink to="#">
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M16.862 4.487l1.687-1.688a1.875 1.875 0 112.652 2.652L10.582 16.07a4.5 4.5 0 01-1.897 1.13L6 18l.8-2.685a4.5 4.5 0 011.13-1.897l8.932-8.931zm0 0L19.5 7.125M18 14v4.75A2.25 2.25 0 0115.75 21H5.25A2.25 2.25 0 013 18.75V8.25A2.25 2.25 0 015.25 6H10" /></svg>
                                </NuxtLink>
                                <NuxtLink @click="deletedops(dops.id)" to="#">
                                <svg xmlns="http://www.w3.org/2000/svg" @click="deletedops(dops.id)" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M14.74 9l-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 01-2.244 2.077H8.084a2.25 2.25 0 01-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 00-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 013.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 00-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 00-7.5 0" /></svg>
                                </NuxtLink>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
        
        </div>

    </div>
</div>
</template>

<script setup>

import {ref, onMounted} from 'vue'
import {collection, getDocs, onSnapshot, doc, addDoc, deleteDoc, updateDoc, orderBy, query, getFirestore} from "firebase/firestore"; 

const db = getFirestore();

const dopscollection = collection(db, 'users', 'testid', 'dops')
const dopsskill = ref ('')
const dopslist2 = ref ([])

//querydops
onMounted(() => {
    onSnapshot(dopscollection, (querySnapshot) => {
    const fbdopslist = [];
    querySnapshot.forEach((doc) => {
                const dopsitems = {
                    id: doc.id,
                    createdon: doc.data().createdon,
                    mentor: doc.data().mentor,
                    skill: doc.data().skill,
                    car: doc.data().car
                }
            fbdopslist.push(dopsitems)
    })
        dopslist2.value = fbdopslist
    });
    }
)

// adddops
// const adddops = () => {
//     addDoc(dopscollection, {skill: dopsskill.value, done: false, date: Date.now()});
//     dopsskill.value = ''
// }

//deletedops
const deletedops = id => {
    deleteDoc(doc(dopscollection, id))
}

</script>

<style scoped>

</style>