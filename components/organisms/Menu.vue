<template>
    <menu>
        <ul :style="`--size: ${items.length};`">
            <li-menu-button v-for="(item, index) in items" :key="index" 
                :name="item.name" :path="item.path"/>
        </ul>
    </menu>
</template>

<script>
export default {
    props: {
        items: {
            type: Array,
            default: () => [
                {
                    name: 'test1',
                    path: '/'
                },
                {
                    name: 'test2',
                    path: '/test2'
                },
                {
                    name: 'test3',
                    path: '/test3'
                }
            ]
        }
    },
}
</script>

<style lang="scss" scoped>
    menu{
        @apply p-0 m-0;

        ul{
            @apply grid grid-cols-$size
                h-12 text-2xl
                select-none;
            box-shadow: inset 0px 0px 20px rgba(0, 0, 0, 0.1);
        }
    }
</style>