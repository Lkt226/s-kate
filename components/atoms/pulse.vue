<template>
    <div class="pulse"></div>
</template>

<style lang="scss" scoped>
    .pulse{
        @apply w-4 h-4 rounded-full
                bg-$tertiary 
                flex items-center justify-center
                shadow-2xl;
        animation: pulse-animation 1s infinite;
        --num: 2;
    }

    @keyframes pulse-animation{
        0%{
            transform: scale(0.3);
            opacity: 0;
        }
        100%{
            transform: scale(1);
            opacity: 1;
        }
    }
</style>