<template>
    <div>
        <div v-if="isLoggedIn" class="flex">
            <navigate />
            <content />
            <slot />
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