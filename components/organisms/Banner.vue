<template>
    <section class="banner-area">
        <div class="banner" :style="`--img: url(${item.image});`">
            <div class="type">
                <h3>Tipo:{{item.type}}</h3>
            </div>
            <section class="text-area">
                <h2 class="title">{{item.title}}</h2>
                <p class="description">{{item.description}}</p>
                <button-simple text="ver mais"/>
            </section>
        </div>
        <span class="counter">
            <div class="item" v-for="(item, index) in items" :key="index"
                @click="counter_click(index)" :class="counter_class_controller(index)"/>
        </span>
    </section>
</template>

<script>
export default {
    props:{
        items: {
            type: Array,
            default: () => [
                {
                    title: 'Downhill',
                    type: 'Longboard (speed)',
                    description: 'Descer uma ladeira andando de Skate, aproveitando toda sua extensão e largura executando manobras, denominadas Slide (derrapar) tanto de pé no como se apoiando no chão ou qualquer manobra que não descaracterize o fato de descer a ladeira.',
                    image: 'https://firebasestorage.googleapis.com/v0/b/fir-kate.appspot.com/o/banner%2Fdownhill.png?alt=media&token=99c87867-ab68-4dd5-904f-de83f496f9bb'
                },
            ]
        }
    },
    data() {
        return {
            current: 0,
        }
    },
    computed: {
        item() {
            return this.items[this.current]
        }
    },
    methods: {
        counter_click(index) {
            this.current = index
        },
        counter_class_controller(index){
            const classes = []
            classes.push(index === this.current ? 'active' : '')

            return classes.join(' ')
        }
    },
    mounted() {
        if(this.items.length > 1) {
            setInterval(() => {
                this.current = (this.current + 1) % this.items.length
            }, 5000)
        }
    }
}
</script>

<style lang="scss" scoped>
    .banner{
        @apply h-125 bg-cover bg-center relative
                grid grid-cols-3
                justify-end items-center;
        background-image: var(--img);

        *:not(button){ @apply text-white; }
        .text-area{ 
            @apply max-w-100 h-4/5 mr-10 grid;
            grid-template-rows: min-content 1fr min-content; 

            .title{ @apply text-4xl font-bold; }
            .description{ @apply h-full; }
        }

        .type{
            @apply col-span-2 w-full h-4/5
                   flex items-end justify-center;
            --gray-t: rgba(31, 41, 55, 0.25);
            >*{
                @apply text-xl bg-$gray-t rounded-md;
            }
        }
    }
    .counter{
        @apply flex justify-center;
        .item{
            @apply  w-3 h-3 m-1 rounded-full
                    bg-gray-400 cursor-pointer;
            &.active{
                @apply bg-$primary;
            }
        }
    }

</style>