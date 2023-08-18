<template>
    <div>
        <div v-if="isLoggedIn">
            <navigate />
        </div>
        <div v-else>
            <login />
        </div>
    </div>
</template>

<script setup>


const isLoggedIn = ref(false)
const myValue = ref("sometime")

</script>

<style scoped>

</style>