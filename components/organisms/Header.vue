<template>
    <header>
        <skate-logo/>
        <span class="actions">
            <search-input/>
            <icon name="shopping-cart" class="action"/>
            <menu-header :items="items_header"/>
        </span>
    </header>
</template>

<script>
export default {
    props:{
        items_header: {
            type: Array,
            default: () => [
                {
                    name: 'Inicio',
                    path: '/'
                },
                {
                    name: 'Produtos',
                    path: '/produtos'
                },
                {
                    name: 'Sobre',
                    path: '/sobre'
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
    header{
        @apply flex justify-between items-center
                w-full h-16 px-7;

        .actions{
            @apply flex;
            >*{
                @apply ml-10;
            }
        }
    }
</style>