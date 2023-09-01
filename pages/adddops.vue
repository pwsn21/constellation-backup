<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navbar />
        
        <div class="flex-1 md:ml-60 md:mt-0 mt-16 justify-center p-10">    
            <form @submit.prevent="adddops">
                <ul>
                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                        <!-- put in an actual datepicker -->
                        <input
                            type="text"
                            v-model="shiftdate"
                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                            id="floatingInput"
                            required
                            placeholder="" />
                        <label
                            for="floatingInput"
                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                            >Date of shift:</label
                        >
                        </div>
                    </li>
                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                        <input
                            type="text"
                            v-model="mentor"
                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                            id="floatingInput"
                            placeholder="" />
                        <label
                            for="floatingInput"
                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                            >Mentor:</label
                        >
                        </div>
                    </li>
                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                        <input
                            type="text"
                            v-model="car"
                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                            id="floatingInput"
                            placeholder="" />
                        <label
                            for="floatingInput"
                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                            >Car:</label
                        >
                        </div>
                    </li>
                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                        <input
                            type="text"
                            v-model="dopsskill"
                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                            id="floatingInput"
                            placeholder="" />
                        <label
                            for="floatingInput"
                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                            >Skill performed:
                            </label
                        >
                        </div>
                    </li>

                    <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100 lg:hidden" />
                </ul>
                <button                                 
                            class="inline-block rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]">
                            Add DOPS 
                            </button>
                            {{ firebaseUser.uid }}
                </form>
    
</div>
</div>
</div>

</template>

<script setup>


import {collection, addDoc, getFirestore} from "firebase/firestore"; 

import { getAuth, onAuthStateChanged } from "firebase/auth";

const firebaseUser = useFirebaseUser();
const auth = getAuth();



const db = getFirestore();

const shiftdate = ref ('')
const mentor = ref ('')
const car = ref ('')
const dopsskill = ref ('')




const userid = onAuthStateChanged(auth, (firebaseUser) => {
   if (firebaseUser) {
    // User is signed in, see docs for a list of available properties
    // https://firebase.google.com/docs/reference/js/auth.user
    const uid = firebaseUser.uid;
    console.log (uid)
    
  } else {

  }
})

console.log(userid)

const dopscollection = collection(db, 'users', 'testid', 'dops')

//adddops
const adddops = () => {
    addDoc(dopscollection, {
        shiftdate: shiftdate.value, 
        mentor:mentor.value, 
        car: car.value, 
        skill: dopsskill.value, 
        createdon: Date.now()
    }
    )
    navigateTo("/menteeforms")
}

</script>

<style scoped>

</style>