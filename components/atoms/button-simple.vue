<template>
    <button class="simple-button">ver mais</button>
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>
    .simple-button{
        @apply h-full w-full rounded-md py-1
                bg-white text-$primary
                uppercase font-bold;

        &:hover{
            @apply bg-gray-200;
        }
    }
</style>