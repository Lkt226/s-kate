<template>
    <div :class="`search-area transition ${state}`">
        <label for="search" class="invi">Pesquisar produtos</label>
        <span @click="toggle()"><icon name="search" class="action"/></span>
        <input type="search" name="search" id="search" :class="size">
    </div>
</template>

<script>
export default {
    props: {
        fixed: {
            type: Boolean,
            default: false
        },
        size: {
            type: String,
            default: 'md'
        }
    },
    data() {
        return {
            search: '',
            state: this.fixed ? 'actived' : 'inactived',
        }
    },
    methods:{
        toggle() {
            if (!this.fixed){
                this.state = this.state === 'inactived' ? 'actived' : 'inactived'
            }
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
            @apply  mb-1 w-0 opacity-0
                    border-b-1 border-$primary;
        }
    }

    .actived{
        #search{
            @apply  ml-2 mb-1 opacity-100;
            &.md{ @apply w-40;}
            &.lg{ @apply w-50;}
        }
    }
</style>