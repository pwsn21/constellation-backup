<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navbar />
        
        
        <div class="flex-1 md:ml-60 md:mt-0 mt-6 justify-center">    
        <div class=" flex justify-center">
            <form @submit.prevent="adddops">
                <input v-model="dopsskill">
                        <button
        class="rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]">
        Button
        </button>
            </form>
            </div>

            <div v-for="dops in dopslist2" class="flex justify-center">
            <div class="w-1/3 mt-10 grid grid-cols-2 border rounded-xl">

                <div class="flex p-10 justify-center rounded-l-lg bg-gray-700" :class="{'bg-green-700' : dops.done}">
                {{ dops.date }} {{ dops.skill }}
                </div>

                <div class="items-center justify-center flex">

                    <button
                        @click="deletedops(dops.id)"
                        type="button"
                        class="inline-block rounded bg-danger px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#dc4c64] transition duration-150 ease-in-out hover:bg-danger-600 hover:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.3),0_4px_18px_0_rgba(220,76,100,0.2)] focus:bg-danger-600 focus:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.3),0_4px_18px_0_rgba(220,76,100,0.2)] focus:outline-none focus:ring-0 active:bg-danger-700 active:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.3),0_4px_18px_0_rgba(220,76,100,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(220,76,100,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.2),0_4px_18px_0_rgba(220,76,100,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.2),0_4px_18px_0_rgba(220,76,100,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(220,76,100,0.2),0_4px_18px_0_rgba(220,76,100,0.1)]">
                        Delete
                    </button>
                </div>
         </div>
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

const dopslist2 = ref([])

console.log(dopslist2)

//adddops
const adddops = () => {

    addDoc(dopscollection, {skill: dopsskill.value, done: false, date: Date.now()});

}

//querydops

onMounted(() => {
    onSnapshot(dopscollection, (querySnapshot) => {
    const fbdopslist = [];
    querySnapshot.forEach((doc) => {
                const dopsitems = {
                    id: doc.id,
                    skill: doc.data().skill,
                    date: doc.data().date
                }
            fbdopslist.push(dopsitems)
    })
        dopslist2.value = fbdopslist
    });
    }
)

const deletedops = id => {
    deleteDoc(doc(dopscollection, id))
}
</script>

<style scoped>

</style>