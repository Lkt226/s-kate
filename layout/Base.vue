<template>
    <div id="body">
        <Header/>
        <Menu :items="items_menu"/>
        <slot/>
    </div>
</template>

<script>
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
        }
    },
}
</script>