<template>
    <font-awesome-icon :class="`icon ${size}`" :icon="[type, name]"/>
</template>

<script>
export default {
    props: {
        name: {
            type: String,
            required: true
        },
        type: {
            type: String,
            default: 'fas'
        },
        size: {
            type: String,
            default: 'lg'
        }
    },
}
</script>

<style lang="scss" scoped>
    .icon{
        &.lg{ @apply w-7 h-7; }
        &.md{ @apply w-6 h-6; }
        &.sm{ @apply w-5 h-5; }
    }
</style>