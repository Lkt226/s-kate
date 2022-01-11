<template>
    <section class="showcase">
        <ProductBar v-for="(products, index) in showcase" :key="index"
            :items="products.items" :title="products.title"/>
    </section>
</template>

<script>
export default {
    props:{
        items: {
            type: Object,
            required: true
        },
    },
    computed:{
        showcase(){
            const showcase = []
            for (const products in this.items) {
                showcase.push({
                    title: products,
                    items: this.items[products]
                })
            }
            return showcase
        }
    }
}
</script>