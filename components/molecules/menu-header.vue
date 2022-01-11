<template>
    <div :class="`transition ${state}`" @click="toggle()">
        <icon name="bars" class="action menu-icon"/>
        <ul class="menu-header-box" :style="`--size: ${items.length};`">
            <li-menu-button v-for="(item, index) in items" :key="index"
                :name="item.name" :path="item.path" class="menu-header-items"/>
        </ul>
    </div>
</template>

<script>
export default {
    props: {
        items: {
            type: Array,
            default: () => [
                {
                    name: "test1",
                    path: "/test1"
                },
                {
                    name: "test2",
                    path: "/test2"
                },
            ]
        },
    },
    data() {
        return {
            state: 'inactived',
        }
    },
    methods: {
        toggle() {
            console.log('toggle')
            this.state = this.state === 'actived' ? 'inactived' : 'actived';
        }
    }
}
</script>

<style lang="scss" scoped>
    .menu-header-box{
        @apply bg-gray-100
                grid grid-rows-$size
                w-60 shadow-md z-100
                fixed top-18 -right-100vw;
        height: calc(var(--size) * 4rem);

        .menu-header-items{
            @apply relative;

            &::after{
                content: '';
                @apply  absolute bottom-0
                        w-full 
                        border-b border-gray-200;
            }
        }
    }

    .actived{
        .menu-icon{
            @apply transform rotate-90;
        }
        .menu-header-box{
            @apply right-6;
        }
    }
</style>