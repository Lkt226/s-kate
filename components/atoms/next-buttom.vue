<template>
    <button :class="class_controller"> <icon :name="'arrow-'+direction"/> </button>
</template>

<script>
export default {
    props:{
        direction:{
            type: String,
            default: 'left'
        },
    },
    computed:{
        class_controller(){
            const classes = []
            classes.push('next-button')
            return classes.join(' ');
        }
    }
}
</script>

<style lang="scss" scoped>
    .next-button{
        @apply h-25 w-15 m-auto
                bg-light-800;
    }
</style>