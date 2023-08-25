<template>
<div class="flex justify-center pt-10">
  
  <div
  class="rounded-lg bg-slate-800 p-6 shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700">
  <h2 class="font-semibold text-xl pb-5">Register</h2>
  <form @submit.prevent="submit">
    <!--Email input-->
    <div class="relative mb-6" data-te-input-wrapper-init>
      <input
        type="email"
        v-model="email"
        class="peer block min-h-[auto] w-full rounded border-0 bg-slate-600 px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-100"
        id="email"
        placeholder="Email address" />
      
    </div>

    <!--Password input-->
    <div class="relative mb-6" data-te-input-wrapper-init>
      <input
        type="password"
        v-model="password"
        class="peer block min-h-[auto] w-full rounded border-0 bg-slate-600 px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-100"
        id="password"
        placeholder="Password" />
      
    </div>

    <!--Submit button-->
    <button
      type="submit"
      class="dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]] inline-block w-full rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]"
      data-te-ripple-init
      data-te-ripple-color="light"
      @click="createTest">
      Sign up
    </button>
  </form>
</div>
</div>
</template>

<script setup>
    const firebaseUser = useFirebaseUser();

    const email = ref( );
    const password = ref( );

const createTest = () =>{
    // from composables/useFirebase. handles the actual call to 
    // the google firebase API's
    createUser(email.value, password.value);
}
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

<style lang="scss" scoped>

</style>