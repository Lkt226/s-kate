<template>
    <div class="card transition">
        <div class="img" :style="`--img: url(${item.imgs[1]});`"/>
        <h3 class="title">{{item.name}}</h3>
        <h2 class="price">{{price}}</h2>
        <star-count :points="item.points"/>
        <button-simple text="adicionar ao carrinho" class="card-button" :pallet="2"/>
    </div>
</template>

<script>
export default {
    props: {
        item:{
            type: Object,
            required: true
        },
    },
    computed: {
        price(){
            let price = this.item.price

            return 'R$ '+price || 'indisponivel'
        }
    }
}
</script>

<style lang="scss" scoped>
    //DEFAULT
    .card{
        @apply grid grid-cols-2 border-2 border-light-500
                w-60 h-auto px-4 py-6 mx-2 my-4;
        grid-template-areas: 'img img' 'name name' 'price points' 'button button';
        grid-template-rows: 2fr repeat(3, min-content);

        .img{
            @apply h-full 
            bg-contain bg-no-repeat bg-center;
            background-image: var(--img);
        }
        .title{
            @apply text-xl px-2;
            font-family: 'Yanone Kaffeesatz', sans-serif;
        }
        .price{
            @apply text-xl px-2;
            font-family: 'Yanone Kaffeesatz', sans-serif;
            font-weight: bold;
        }
    }

    //BUTTON
    .card{
        @apply relative overflow-hidden;
        .card-button{
            @apply absolute h-0 -bottom-30;
        }

        &:hover{
            .card-button{
                @apply relative h-auto bottom-0;
            }
        }
    }

    //grid areas
    .card{
        .img{ grid-area: img; }
        h3{ grid-area: name; }
        h2{ grid-area: price; }
        span{ grid-area: points; }
        .card-button{ grid-area: button; }
    }
</style>