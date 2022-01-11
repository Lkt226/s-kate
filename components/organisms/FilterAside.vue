<template>
    <aside class="filter-aside">
        <label-dropdown v-for="(order, index) in items_controller" :key="index"
            :title="order.title" :items="order.items"/>
    </aside>
</template>

<script>
export default {
    props: {
        orders: {
            type: Array,
            default: () => [
                {
                    title: "test",
                    items: [
                        { value: "test1", text: "/test1" },
                        { value: "test2", text: "/test2" },
                    ]
                },
            ]
        },
    },
    computed: {
        items_controller(){
            const items_controller = []
            for (const order in this.orders) {
                items_controller.push({
                    title: this.orders[order]?.title,
                    items: [
                        { value: "", text: "" },
                        ...this.orders[order]?.items
                    ]
                })
            }
            return items_controller
        }
    }
}
</script>

<style lang="scss" scoped>
    .filter-aside{
        @apply flex justify-between items-center;

        span{
            @apply flex;
        }
    }
</style>