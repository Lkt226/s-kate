<template>
    <Showcase :items="items" v-if="!items"/>
    <Loading v-else/>
</template>

<script>
export default {
    data() {
        return {
            products: false,
            linguagem: 'ptbr'
        }
    },
    computed: {
        items() {
            const tags = (this.$route.query.tags)?.split('-');
            console.log(tags);
            return this.products;
        }
    },
    async fetch(){
        this.products = (await axios.get('https://fir-kate-default-rtdb.firebaseio.com/Products.json')).data;
    },
}
</script>