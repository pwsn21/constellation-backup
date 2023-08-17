<template>
    <div>
        <p>Mentee details for {{ id }}</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste sed at libero maxime hic optio explicabo officia et maiores. Vel ullam laborum excepturi sapiente aut dolorem, reiciendis corporis! Illo, deserunt.</p>
    </div>
</template>

<script setup>
    const { id } = useRoute().params
    definePageMeta({
        layout: 'acpo'
    })
</script>

<style scoped>

</style>