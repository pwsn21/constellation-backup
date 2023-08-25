<template>
    <div>
        <NuxtPage />
    </div>
</template>
<script setup>
import "tw-elements/dist/css/tw-elements.min.css";

const firebaseUser = useFirebaseUser();
const authNeeded = useAuthNeeded();

onMounted(async () => {
    await initUser()
})
</script>