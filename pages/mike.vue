<template>
    <div class="gaps-4">
        <div class="flex gap-2">
            <div>Current User :</div>
            <div>{{ firebaseUser != "AuthNeeded" || !firebaseUser ? "Not Signed In" : firebaseUser.email }}</div>
        </div>
        <div class="flex gap-2">
            <div>UID :</div>
            <div>{{ firebaseUser != "AuthNeeded" ? "Not Signed In" : firebaseUser.uid }}</div>
        </div>
        <hr />
        <div class="flex gap-2">
            <div><button @click="createTest" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Create Test User</button></div>
            <div><button @click="loginTest" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Login Test User</button></div>
            <div><button @click="logout" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Log Out</button></div>
            <div><button @click="loginAdmin" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Login Admin User</button></div>
        </div>  
    </div>
</template>
<script setup>
const firebaseUser = useFirebaseUser();


/*
Function for creating a new user. A similar function can
be created for handling a form submission, in this case a 
registration form.
*/
const createTest = () =>{
    // from composables/useFirebase. handles the actual call to 
    // the google firebase API's
    createUser("test1@bcehs.ca", "password");
}

/*
Function for loggin in user. A similar function can
be created for handling a form submission, in this case a 
login form.
*/
const loginTest = () =>{
    // from composables/useFirebase. handles the actual call to 
    // the google firebase API's
    signInUser("test1@bcehs.ca", "password");
}

/*
Function for signing out a user. can be called from within a 
function like here or directly from a button action.
*/
const logout = () =>{
    // from composables/useFirebase. handles the actual call to 
    // the google firebase API's
    signOutUser();
}

/*
Function for loggin in user. A similar function can
be created for handling a form submission, in this case a 
login form.
*/
const loginAdmin = () =>{
    // from composables/useFirebase.
    signInUser("admin@bcehs.ca", "password");
}

</script>