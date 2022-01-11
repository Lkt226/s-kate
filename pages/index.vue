<template>
  <Base v-if="banner && products">
    <main>
      <Banner :items="banner"/>
      <ProductArea :items="products"/>
    </main>
  </Base>
  <Loading v-else/>
</template>

<script>
const axios = require('axios').default;
export default {
  data() {
    return {
      banner: false,
      products: false,
      linguagem: 'ptbr'
    }
  },
  async fetch(){
    this.products = (await axios.get('https://fir-kate-default-rtdb.firebaseio.com/Products.json')).data;
    this.banner = (await axios.get(`https://fir-kate-default-rtdb.firebaseio.com/Linguagem/${this.linguagem}/banner.json`)).data;
  },
}
</script>