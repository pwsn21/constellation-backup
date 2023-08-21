<template>
                <div class="grid grid-cols-3 gap-4 font-normal text-base">
                    <div v-for="stuff in products">
                        <div>{{ stuff.title }}</div>
                        <div>{{ stuff.category }}</div>
                    </div>
                
                </div>

</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>