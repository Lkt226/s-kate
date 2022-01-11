<template>
  <div>
   <Header/>
   <Menu :items="items_menu"/>
   <Banner/>
   <ProductArea :items="products"/>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  data() {
    return {
      items_menu: [
        {
          name: 'Trucks',
          path: '/produtos/trucks'
        },
        {
          name: 'Rodas',
          path: '/produtos/rodas'
        },
        {
          name: 'Rolamentos',
          path: '/produtos/rolamentos'
        },
        {
          name: 'Shapes',
          path: '/produtos/shapes'
        },
        {
          name: 'Acessórios',
          path: '/produtos/acessorios'
        }
      ],
      products: {}
    }
  },
  async beforeCreate (){
    const response = await axios.get('https://fir-kate-default-rtdb.firebaseio.com/Products.json');
    this.products = response.data;
  }
}
</script>