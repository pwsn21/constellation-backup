<template>
  
    <div class="relative min-h-screen md:flex">
<!-- mobile -->
        <div class="bg-blue-950 text-blue-100 flex justify-between md:hidden duration-500 ease-in-out">
            <div class="flex items-center">
                <NuxtLink to="/" class="font-extrabold flex p-5 justify-start">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M9.813 15.904L9 18.75l-.813-2.846a4.5 4.5 0 00-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 003.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 003.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 00-3.09 3.09zM18.259 8.715L18 9.75l-.259-1.035a3.375 3.375 0 00-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 002.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 002.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 00-2.456 2.456zM16.894 20.567L16.5 21.75l-.394-1.183a2.25 2.25 0 00-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 001.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 001.423 1.423l1.183.394-1.183.394a2.25 2.25 0 00-1.423 1.423z" /></svg>
                        CONSTELLATION
                </Nuxtlink>
                    <NuxtLink to="/acpo" class="flex p-4 hover:text-gray-300 hover:bg-blue-900 rounded-lg transition duration-500">ACP Orientation</NuxtLink>
                    <NuxtLink to="/schedule" class="flex p-4 hover:text-gray-300 hover:bg-blue-900 rounded-lg transition duration-500">Schedule</NuxtLink>
                
            </div>
            <div>
            <button class="mobile-menu-button p-4 focus:bg-gray-600" >
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6"><path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5" /></svg>
            </button>
            </div>
        </div>
<!-- sidenav -->
        <div class="sidebar bg-blue-950 text-blue-100 w-64 space-y-6 px-2 md:relative md:translate-x-0 inset-y-0 left-0 transform -translate-x-full transition duration-200 ease-in-out">
            <nav>
                <NuxtLink to="/" class="font-extrabold flex p-5">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6">  <path stroke-linecap="round" stroke-linejoin="round" d="M9.813 15.904L9 18.75l-.813-2.846a4.5 4.5 0 00-3.09-3.09L2.25 12l2.846-.813a4.5 4.5 0 003.09-3.09L9 5.25l.813 2.846a4.5 4.5 0 003.09 3.09L15.75 12l-2.846.813a4.5 4.5 0 00-3.09 3.09zM18.259 8.715L18 9.75l-.259-1.035a3.375 3.375 0 00-2.455-2.456L14.25 6l1.036-.259a3.375 3.375 0 002.455-2.456L18 2.25l.259 1.035a3.375 3.375 0 002.456 2.456L21.75 6l-1.035.259a3.375 3.375 0 00-2.456 2.456zM16.894 20.567L16.5 21.75l-.394-1.183a2.25 2.25 0 00-1.423-1.423L13.5 18.75l1.183-.394a2.25 2.25 0 001.423-1.423l.394-1.183.394 1.183a2.25 2.25 0 001.423 1.423l1.183.394-1.183.394a2.25 2.25 0 00-1.423 1.423z" /></svg>
                        CONSTELLATIONj
                </Nuxtlink >
                <ul>
                    <li class="flex p-4 hover:text-gray-300 hover:bg-blue-900 rounded-lg transition duration-500"><NuxtLink to="/acpo">ACP Orientation</NuxtLink></li>
                    <li class="flex p-4 hover:text-gray-300 hover:bg-blue-900 rounded-lg transition duration-500"><NuxtLink to="/schedule">Schedule</NuxtLink></li>
                </ul>
            </nav>
        </div>
    <div class="p-10 text-2xl flex-1">stuff for now</div>
    </div>
      
    <!-- <div>
        <header class="shadow-sm bg-blue-950">
            <nav class="container bg-blue-950 mx-auto p-4 flex justify-start">
                <NuxtLink to="/" class="font-bold"><h2>Constellation</h2></NuxtLink>
            </nav>
            
            <nav class="container bg-blue-950 w-1/6">
                <ul
                    class="relative m-0 list-none px-5 pb-12"
                    data-te-sidenav-menu-ref
                    data-te-sidenav->
                <ul
                    class="relative m-0 list-none px-[0.2rem] pb-12"
                    data-te-sidenav-menu-ref>
                    <li class="flex pad-4"><NuxtLink to="/">Home</NuxtLink></li>
                    <li class="flex pad-4"><NuxtLink to="/about">About</NuxtLink></li>
                    <li class="flex pad-4"><NuxtLink to="/products" class="btn">Products</NuxtLink></li>
                </ul>
            </nav>
            
        
        </header>
    
        
    </div> -->
    
    <div>
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