<template>
    <div>
        <div v-if="isLoggedIn">
        
        
        <navbar />
        <div class="flex-1 md:ml-60 md:mt-0 mt-6">
            <div class="p-10 m-10 mt-14 border rounded-lg shadow bg-gray-800 border-gray-700">
                
                <h5 class="mb-2 text-2xl font-bold tracking-tight">Your Dashboard</h5>
                
                <hr class="h-px my-8 bg-gray-200 border-0 dark:bg-gray-500">  
                <p class="py-2">some text {{ firebaseUser ? firebaseUser.email : "Pending..." }} {{ firebaseUser.uid }}</p>



                <button
                @click="logout"
                class="border rounded-lg p-2 bg-blue-900 hover:bg-blue-950"
                >
                Log-out
                </button>
                

            </div>

            <div class="p-10 m-10  border border-gray-200 rounded-lg shadow dark:bg-gray-800 dark:border-gray-700">
                <a href="#">
                    <h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900">Noteworthy technology acquisitions 2021</h5>
                </a>
                <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">Here are the biggest enterprise technology acquisitions of 2021 so far, in reverse chronological order.</p>
                <a href="#" class="inline-flex items-center px-3 py-2 text-sm font-medium text-center text-white bg-blue-700 rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                    Read more
                    <svg class="w-3.5 h-3.5 ml-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 14 10">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 5h12m0 0L9 1m4 4L9 9"/>
                    </svg>
                </a>
            </div>
        </div>
            
        </div>
        

        <div v-else>
            <login />
        </div>
    </div>
</template>

<script setup>
const isLoggedIn = ref(true)
const firebaseUser = useFirebaseUser();

const logout = () =>{
    // from composables/useFirebase. handles the actual call to 
    // the google firebase API's
    signOutUser();
}


</script>

<style scoped>

</style>