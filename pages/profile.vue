<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navbar />
        
        
        <div class="flex-1 md:ml-60 md:mt-0 mt-5 ">
            
            <!-- content -->
            <div class="text-blue-100">
                
                <h2 class="pt-10 text-4xl font-semibold text-center">Profile for {{ firstName }} {{ lastName }}</h2>

                <hr class="my-5 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                
                <div class="grid grid-cols-1 gap-5 lg:grid lg:gap-5 p-10 lg:grid-cols-2 text-blue-100 rounded-lg dark:bg-gray-800 dark:border-gray-700">
                    
                    <!-- about card -->
                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700 lg:col-span-2">
                        <h2 class="text-2xl font-semibold pb-1">About</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                        <div class="grid lg:grid-cols-2">
                            <div>
                                <ul>
                                    <li>Name: {{ firstName }} {{ lastName }}</li>
                                    <li>Gender: <div v-for="profile in profile.results" class="inline py-1">{{ profile.gender }} </div></li>
                                    <li>Cell: {{ phonenumber}}</li>
                                    <li>Email: <div v-for="profile in profile.results" class="inline py-1">{{ firebaseUser.email }} </div></li>
                                    <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100 lg:hidden" />
                                </ul>
                            </div>
                            <div>                                
                                Address:
                                <ul>
                                    <li><div v-for="profile in profile.results" class="inline py-1">{{ profile.location.street.number }} {{ profile.location.street.name }}</div></li>
                                    <li><div v-for="profile in profile.results" class="inline py-1">{{ profile.location.city }}, {{ profile.location.state }} </div></li>
                                    <li><div v-for="profile in profile.results" class="inline py-1">{{ profile.location.country }} </div></li>
                                    <li><div v-for="profile in profile.results" class="inline py-1">{{ profile.location.postcode }} </div></li>
                                </ul>                                
                            </div>
                        </div>
                    </div>
                    <!-- employeeinformation -->
                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">
                        <h2 class="text-2xl font-semibold">Employee Information</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                        <ul>
                                    <li>Employee Number: <div v-for="profile in profile.results" class="inline py-1">{{ profile.id.value }} </div></li>
                                    <li>Platoon\Rotation:</li>
                                    <li>Station Number: <div v-for="pped in pped.results" class="inline py-1"> {{ pped.dob.age }}</div></li>
                                    <li>Unit Chief: <div v-for="name in unitchief.results" class="inline py-1">{{ name.name.first }} {{ name.name.last }} </div></li>
                                    <li>Region: <div v-for="pped in pped.results" class="inline py-1">{{ pped.location.city }} </div></li>
                                    <li>Manager: <div v-for="name in manager.results" class="inline py-1">{{ name.name.first }} {{ name.name.last }} </div></li>

                        </ul>
                    </div>

                    <!-- acpo card -->
                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700">
                        <h2 class="text-2xl font-semibold">ACP-Orientation</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                        <ul>
                                    <li>Milestone:</li>
                                    <li>Current Support Level:</li>
                                    <li>Assigned PPEd: <div v-for="pped in pped.results" class="inline py-1"> {{ pped.name.first }} {{ pped.name.last }}</div></li>
                                    <li>Next Scheduled Milestone Meeting: <div v-for="profile in profile.results" class="inline py-1">{{ profile.registered.date }} </div></li>
                        </ul>
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

import { doc, getDoc, getFirestore } from "firebase/firestore"; 


const firebaseUser = useFirebaseUser();
const db = getFirestore();

// need to add unique ids
const docRef = doc(db, "users", "tesasdftid");
const docSnap = await getDoc(docRef);

const firstName = ref (docSnap.data().firstName)
const lastName = ref (docSnap.data().lastName)
const phonenumber = ref (docSnap.data().phonenumber)

if (docSnap.exists()) {
  console.log("Document data:", docSnap.data());
    
    //need to nest these constants
    const firstName = docSnap.data().firstName
    const lastName = docSnap.data().lastName
    const phonenumber = docSnap.data().phonenumber
    console.log(firstName)

} else {
  // docSnap.data() will be undefined in this case
  console.log("No such document!");
}


    const {data:profile}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca')
    const {data:pped}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca')
    const {data:unitchief}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca1')
    const {data:manager}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca1')
    
</script>

<style scoped>

</style>