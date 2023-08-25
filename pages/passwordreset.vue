<template>
    <div class="flex justify-center py-5">
    <div class="border w-1/5 rounded-lg shadow-lg p-4">
    <h2 class="text-xl">Password Reset</h2>
    <div class="py-4"><input
        type="email"
        v-model="email"
        class="p-1"
        id="email"
        placeholder="Email address" />
    </div>
        <button
                @click="passwordreset"
                class="border rounded-lg p-2 bg-blue-900 hover:bg-blue-950"
                >
                Reset Password
                </button>
    </div>
    </div>
</template>

<script setup>

const email = ref( );
const passwordreset = () =>{
    // from composables/useFirebase. handles the actual call to 
    // the google firebase API's
    resetPasswordEmail(email.value);
}
</script>

<style scoped>

</style>