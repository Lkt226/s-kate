<template>
    <div :class="`search-area transition ${state}`" @click="toggle()">
        <label for="search" class="invi">Pesquisar produtos</label>
        <icon name="search" class="action"/>
        <input type="search" name="search" id="search">
    </div>
</template>

<script>
export default {
    data() {
        return {
            search: '',
            state: 'inactived',
        }
    },
    methods:{
        toggle() {
            this.state = this.state === 'inactived' ? 'actived' : 'inactived'
        },
    }
}
</script>

<style lang="scss" scoped>
    .invi{
        @apply opacity-0;
        font-size: 0;
    }
    .search-area{
        @apply flex relative right-0;
        #search{
            @apply  pl-2 mb-1 w-0 opacity-0
                    border-b-1 border-$primary;
        }
    }

    .actived{
        #search{
            @apply  pl-2 mb-1 w-full opacity-100;
        }
    }
</style>