<template>
    <div class="mt-4 ml-4">
        <div v-if="loginError" class="mb-2 bg-red-200 border border-red-500 text-red-700">
            <div class="pl-4">
                {{ loginErrorMessage }}
            </div> 
        </div>
        <div>
            <form @submit.prevent="submit">
                <div class="mb-2">
                    <input type="email" v-model="email" placeholder="Email Address"/>
                </div>
                <div class="mb-2">
                    <input type="password" v-model="password" placeholder="Password"/>
                </div>
                <div>
                    <button class="border" type="submit" @click="loginUser">Submit</button>
                </div>
            </form>
        </div>
    </div>
</template>

<script setup>
    const firebaseUser = useFirebaseUser()
    // using these ref variables is the easiest way to collect the data
    // there are more elegant solutions but they are time consuming.
    const email = ref( );
    const password = ref( );
    const loginError = ref(false);
    const loginErrorMessage = ref();

    const loginUser = async () => {
        const result = await signInUser(email.value, password.value);
        
        //handle the simple boolean error
        if (!result){
            loginError.value = true;
            loginErrorMessage.value = "Error Loggin In"
        } else {
            // the call to signInUser above will return credentials if
            // successful. here we store them in the state managed variable
            // so that its available to all pages/components.
            firebaseUser.value = result;

            // once creds are set, we can nav back to the root to 
            // verify them and proceed into the rest of the application
            navigateTo("/")
        }
    };
</script>