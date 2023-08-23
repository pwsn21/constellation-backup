<template>
    <div>
        <NuxtPage />
    </div>
</template>
<script setup>
const firebaseUser = useFirebaseUser();
const authNeeded = useAuthNeeded();

onMounted(async () => {
    await initUser()
})
</script>