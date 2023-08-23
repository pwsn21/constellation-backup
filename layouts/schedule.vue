<template>
    <div>
    <div class="flex">
        <!-- sidenav -->
        <navigate />
        
        
        <div class="flex-1">
            <!-- subnav schedule -->
            <subnavschedule />
            
            <!-- content -->
            <div class="mx-auto font-extrabold text-3xl">
            
            <slot />

            </div>
        
        
        </div>
    
    </div>
         
    </div> 
</template>

<script setup>

</script>

<style scoped>
    .router-link-exact-active {
        color: black;
    }
</style>