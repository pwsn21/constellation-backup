<template>
    <div>
        <div v-if="isLoggedIn" class="flex">
            <navigate />
            <nuxt />
        </div>
        <div v-else>
            <login />
        </div>
    </div>
</template>

<script setup>


const isLoggedIn = ref(true)
const myValue = ref("sometime")

</script>

<style scoped>

</style>