<template>
    <li class="li-menu-button action" @click="handleClick()">{{name}}</li>
</template>

<script>
export default {
    props: {
        name: {
            type: String,
            default: 'test'
        },
        path: {
            type: String,
            default: '/'
        }
    },
    methods: {
        handleClick() {
            window.location.href = this.path
        }
    }
}
</script>

<style lang="scss" scoped>
    .li-menu-button{
        @apply  w-full h-full
                flex justify-center items-center;
                
        &:hover{
            @apply bg-gray-200;
        }
    }
</style>