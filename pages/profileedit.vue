<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navbar />
        
        
        <div class="flex-1 md:ml-60 md:mt-0 mt-5 ">
            
            <!-- content -->
            <div class="text-blue-100">
                
                <h2 class="pt-10 text-4xl font-semibold text-center">Profile for {{ firebaseUser.email }} {{ firebaseUser.uid }}</h2>

                <hr class="my-5 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                
                <div class="grid grid-cols-1 gap-5 lg:grid lg:gap-5 p-10 lg:grid-cols-2 text-blue-100 rounded-lg dark:bg-gray-800 dark:border-gray-700">
                    
                    <!-- about card -->
                    <div class="p-10 border rounded-lg shadow bg-gray-800 border-gray-700 lg:col-span-2">
                        <h2 class="text-2xl font-semibold pb-1">About</h2>
                        <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100" />
                        <div class="grid lg:grid-cols-2">
                            <div>
                                <form @submit.prevent="saveprofile">
                                <ul>
                                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                                        <input
                                            type="text"
                                            v-model="firstName"
                                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                                            id="floatingInput"
                                            placeholder="" />
                                        <label
                                            for="floatingInput"
                                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                                            >First Name:</label
                                        >
                                        </div>
                                    </li>
                                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                                        <input
                                            type="text"
                                            v-model="lastName"
                                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                                            id="floatingInput"
                                            placeholder="" />
                                        <label
                                            for="floatingInput"
                                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                                            >Last Name:</label
                                        >
                                        </div>
                                    </li>
                                    <li><div class="relative mb-3" data-te-input-wrapper-init>
                                        <input
                                            type="text"
                                            v-model="phonenumber"
                                            class="peer m-0 h-[55px] w-1/3 rounded border border-solid border-neutral-300 bg-gray-700 bg-clip-padding px-3 py-4 font-normal leading-tight text-white-300 transition duration-200 ease-linear placeholder:text-transparent focus:border-primary focus:pb-[0.625rem] focus:pt-[1.625rem] focus:outline-none peer-focus:text-primary dark:border-neutral-600 dark:text-neutral-200 dark:focus:border-primary dark:peer-focus:text-primary [&:not(:placeholder-shown)]:pb-[0.625rem] [&:not(:placeholder-shown)]:pt-[1.625rem]"
                                            id="floatingInput"
                                            placeholder="" />
                                        <label
                                            for="floatingInput"
                                            class="pointer-events-none absolute left-0 top-0 origin-[0_0] border border-solid border-transparent px-3 py-4 text-blue-400 transition-[opacity,_transform] duration-200 ease-linear peer-focus:-translate-y-2 peer-focus:translate-x-[0.15rem] peer-focus:scale-[0.85] peer-focus:text-primary peer-[:not(:placeholder-shown)]:-translate-y-2 peer-[:not(:placeholder-shown)]:translate-x-[0.15rem] peer-[:not(:placeholder-shown)]:scale-[0.85] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-primary"
                                            >Phone Number:</label
                                        >
                                        </div>
                                    </li>
                                       
                                    <li>Gender:</li>
                                    <li>Cell: <div v-for="profile in profile.results" class="inline py-1">{{ profile.phone }} </div></li>
                                    <li>Email: <div v-for="profile in profile.results" class="inline py-1">{{ profile.email }} </div></li>
                                    <hr class="my-4 h-px border-t-0 bg-transparent bg-gradient-to-r from-transparent via-neutral-500 to-transparent opacity-25 dark:opacity-100 lg:hidden" />
                                </ul>
                                <button                                 
                                            class="inline-block rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]">
                                            Save
                                            </button>
                                </form>
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

import { doc, setDoc, getDoc, getFirestore } from "firebase/firestore"; 


const firebaseUser = useFirebaseUser();
const db = getFirestore();

console.log(firebaseUser)

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


const saveprofile = () =>{
    setDoc(doc(db, "users", 'tesasdftid'), {firstName:firstName.value, lastName:lastName.value, phonenumber:phonenumber.value});

}

//dummy info delete afterwards
    const {data:profile}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca')
    const {data:pped}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca')
    const {data:unitchief}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca1')
    const {data:manager}  = await useFetch('https://randomuser.me/api/?results=1&nat=ca1')
    


</script>

<style scoped>

</style>