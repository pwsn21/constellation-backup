<template>
    <nav class="bg-blue-950 border-b-2 border-b-gray-500">
        <div class="max-w-4xl mx-auto text-white">
            
            <div class="flex justify-between items-center">
                <div class="flex justify-start items-center">
                <!-- logo -->
                <div class="p-4">
                    <NuxtLink to="/" class="font-extrabold flex">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">  <path stroke-linecap="round" stroke-linejoin="round" d="M9.813 15.904L9 18.75l-.813-2.846a4.5 4.5 0 00-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 003.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 003.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 00-3.09 3.09zM18.259 8.715L18 9.75l-.259-1.035a3.375 3.375 0 00-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 002.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 002.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 00-2.456 2.456zM16.894 20.567L16.5 21.75l-.394-1.183a2.25 2.25 0 00-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 001.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 001.423 1.423l1.183.394-1.183.394a2.25 2.25 0 00-1.423 1.423z" /></svg>
                        CONSTELLATION
                    </Nuxtlink >
                </div>
                                <!-- primary nav -->
                <div>
                    <ul class="flex p-4 ">
                        <li class="flex p-4 hover:text-gray-300"><NuxtLink to="/acpo">ACP Orientation</NuxtLink></li>
                        <li class="flex p-4 hover:text-gray-300"><NuxtLink to="/schedule">Schedule</NuxtLink></li>
                    </ul>
                </div>
            </div>

                <!-- users nav -->
                <div>
                    <ul class="flex p-4">
                        <li class="flex p-4"><NuxtLink to="/login">Login</NuxtLink></li>
                        <li class="flex p-4 bg-cyan-900 font-bold rounded-2xl"><NuxtLink to="/signup">Sign-up</NuxtLink></li>
                    </ul>
                </div>
            </div>
    </div>
    </nav>
    <!-- subnav -->
    <nav class="bg-blue-900 border-b-2 border-b-gray-500">
        <div class="flex text-white">
            <li class="flex p-4 hover:text-gray-300"><NuxtLink to="/acpo">Dashboard</NuxtLink></li>
            <li class="flex p-4 hover:text-gray-300"><NuxtLink to="/msmeeting">Milestone Meetings</NuxtLink></li>
        </div>


    </nav>
    <div class="container mx-auto p-4">
            <slot />
        </div>

</template>

<script setup>

</script>

<style scoped>
    .router-link-exact-active {
        color: gray;
    }
</style>