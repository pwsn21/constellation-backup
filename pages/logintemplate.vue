<template>
        <div v-if="loginError" class="mb-2 bg-red-200 border border-red-500 text-red-700">
            <div class="pl-4">
                {{ loginErrorMessage }}
            </div> 
        </div>

<div class="flex justify-center pt-10">    
<div
  class="block w-1\3 rounded-lg bg-slate-800 p-6 shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700">
  <h2 class="font-semibold text-xl pb-5">Login</h2>
  <form  @submit.prevent="submit">
    <!--E-mail input-->
    <div class="relative mb-6" data-te-input-wrapper-init>
      <input
        type="email"
        v-model="email"
        class="peer block min-h-[auto] w-full rounded border-0 bg-slate-600 px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-100"
        placeholder="Email" />
    </div>

    <!--Password input-->
    <div class="relative mb-6" data-te-input-wrapper-init>
      <input
        type="password"
        v-model="password"
        class="peer block min-h-[auto] w-full rounded border-0 bg-slate-600 px-3 py-[0.32rem] leading-[1.6] outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-100"
        id="exampleInputPassword2"
        placeholder="Password" />
      
    </div>

    <!--Remember me checkbox-->
    <div class="mb-6 flex items-center justify-between">
      <div class="block min-h-[1.5rem] pl-[1.5rem]">
        <input
          class="relative float-left -ml-[1.5rem] mr-[6px] mt-[0.15rem] h-[1.125rem] w-[1.125rem] appearance-none rounded-[0.25rem] border-[0.125rem] border-solid border-neutral-300 outline-none before:pointer-events-none before:absolute before:h-[0.875rem] before:w-[0.875rem] before:scale-0 before:rounded-full before:bg-transparent before:opacity-0 before:shadow-[0px_0px_0px_13px_transparent] before:content-[''] checked:border-primary checked:bg-primary checked:before:opacity-[0.16] checked:after:absolute checked:after:-mt-px checked:after:ml-[0.25rem] checked:after:block checked:after:h-[0.8125rem] checked:after:w-[0.375rem] checked:after:rotate-45 checked:after:border-[0.125rem] checked:after:border-l-0 checked:after:border-t-0 checked:after:border-solid checked:after:border-white checked:after:bg-transparent checked:after:content-[''] hover:cursor-pointer hover:before:opacity-[0.04] hover:before:shadow-[0px_0px_0px_13px_rgba(0,0,0,0.6)] focus:shadow-none focus:transition-[border-color_0.2s] focus:before:scale-100 focus:before:opacity-[0.12] focus:before:shadow-[0px_0px_0px_13px_rgba(0,0,0,0.6)] focus:before:transition-[box-shadow_0.2s,transform_0.2s] focus:after:absolute focus:after:z-[1] focus:after:block focus:after:h-[0.875rem] focus:after:w-[0.875rem] focus:after:rounded-[0.125rem] focus:after:content-[''] checked:focus:before:scale-100 checked:focus:before:shadow-[0px_0px_0px_13px_#3b71ca] checked:focus:before:transition-[box-shadow_0.2s,transform_0.2s] checked:focus:after:-mt-px checked:focus:after:ml-[0.25rem] checked:focus:after:h-[0.8125rem] checked:focus:after:w-[0.375rem] checked:focus:after:rotate-45 checked:focus:after:rounded-none checked:focus:after:border-[0.125rem] checked:focus:after:border-l-0 checked:focus:after:border-t-0 checked:focus:after:border-solid checked:focus:after:border-white checked:focus:after:bg-transparent dark:border-neutral-600 dark:checked:border-primary dark:checked:bg-primary dark:focus:before:shadow-[0px_0px_0px_13px_rgba(255,255,255,0.4)] dark:checked:focus:before:shadow-[0px_0px_0px_13px_#3b71ca]"
          type="checkbox"
          value=""
          id="exampleCheck2" />
        <label
          class="inline-block pl-[0.15rem] hover:cursor-pointer"
          for="exampleCheck2">
          Remember me
        </label>
      </div>

      <!--Forgot password link-->
      <NuxtLink
        href="/passwordreset"
        class="text-primary transition duration-150 ease-in-out hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600"
        >Forgot password?</NuxtLink
      >
    </div>

    <!--Sign in button-->
    <button
      type="submit"
      @click="loginUser"
      class="dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]] inline-block w-full rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]"
      data-te-ripple-init
      data-te-ripple-color="light">
      Sign in
    </button>

    <!--Register link-->
    <p class="mt-6 text-center text-slate-300 dark:text-neutral-200">
      Not a member?
      <NuxtLink
        to="/register"
        class="text-primary transition duration-150 ease-in-out hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600"
        >Register</NuxtLink>
      
    </p>
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

<style scoped>

</style>