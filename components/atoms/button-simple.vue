<template>
    <button :class="class_controller">{{text}}</button>
</template>

<script>
export default {
    props:{
        pallet:{
            type: Number,
            default: 1
        },
        text: {
            type: String,
            required: true
        },
    },
    computed:{
        class_controller(){
            const classes = []
            classes.push('simple-button')
            classes.push(`pallet${this.pallet}`)
            return classes.join(' ');
        }
    }
}
</script>

<style lang="scss" scoped>
    .simple-button{
        @apply h-full w-full rounded-md py-1
                uppercase font-bold;
        &.pallet1{
            @apply bg-white text-$primary;
            
            &:hover{ @apply bg-gray-200; }
        }
        &.pallet2{
            @apply bg-$secondary text-white;

            &:hover{ @apply bg-$primary; }
        }

    }
</style>