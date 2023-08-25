<template>
<div
  class="block max-w-md rounded-lg bg-white p-6 shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700">
  <form @submit.prevent="submit">
    <!--Email input-->
    <div class="relative mb-6" data-te-input-wrapper-init>
      <input
        type="email"
        v-model="email"
        class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
        id="email"
        placeholder="Email address" />
      <label
        for="exampleInput125"
        class="pointer-events-none absolute left-3 top-0 mb-0 max-w-[90%] origin-[0_0] truncate pt-[0.37rem] leading-[1.6] text-neutral-500 transition-all duration-200 ease-out peer-focus:-translate-y-[0.9rem] peer-focus:scale-[0.8] peer-focus:text-primary peer-data-[te-input-state-active]:-translate-y-[0.9rem] peer-data-[te-input-state-active]:scale-[0.8] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-neutral-200"
        >Email address
      </label>
    </div>

    <!--Password input-->
    <div class="relative mb-6" data-te-input-wrapper-init>
      <input
        type="password"
        v-model="password"
        class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
        id="password"
        placeholder="Password" />
      <label
        for="exampleInput126"
        class="pointer-events-none absolute left-3 top-0 mb-0 max-w-[90%] origin-[0_0] truncate pt-[0.37rem] leading-[1.6] text-neutral-500 transition-all duration-200 ease-out peer-focus:-translate-y-[0.9rem] peer-focus:scale-[0.8] peer-focus:text-primary peer-data-[te-input-state-active]:-translate-y-[0.9rem] peer-data-[te-input-state-active]:scale-[0.8] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-neutral-200"
        >Password
      </label>
    </div>

    <!--Submit button-->
    <button
      type="submit"
      class="border rounded-lg p-2 bg-blue-900 hover:bg-blue-950"
      data-te-ripple-init
      data-te-ripple-color="light"
      @click="createTest">
      Sign up
    </button>
  </form>
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