<template>
    <section :class="class_controller()">
        <h3 v-if="title">{{title}}</h3>
        <span>
            <product-card v-for="(item, index) in items" :key="index" :item="item"/>
        </span>
    </section>
</template>

<script>
export default {
    props:{
        inline: {
            type: Boolean,
            default: true
        },
        items: {
            type: Object,
            required: true
        },
        title: {
            type: String,
            required: false
        },
    },
    methods: {
        class_controller: function() {
            const classes = []
            classes.push('product-bar')

            classes.push(this.inline ? 'inline-products' : '')

            return classes.join(' ');
        }
    }
}
</script>

<style lang="scss" scoped>
    .product-bar{
        @apply pt-10;

        h3{
            @apply text-3xl font-bold ml-4 uppercase;
        }

        span{
            @apply h-100
                grid grid-flow-col gap-4
                relative overflow-x-auto overflow-y-hidden;
        }

        * { scrollbar-color: rgb(236, 236, 236); }
        *::-webkit-scrollbar { height: 15px; }
        *::-webkit-scrollbar-track { background: rgb(236, 236, 236); }
        *::-webkit-scrollbar-thumb { @apply bg-$primary; }
    }
</style>