<template>
    <section class="filter-bar">
        <search-input fixed size="lg"/>
        <span>
            <label-dropdown title="Ordenar por:" :items="[
                {value: 'lancamento', text: 'lançamento'},
                {value: 'preco', text: 'preço'},
            ]" inline/>
            <label-range title="Preço"/>
        </span>
    </section>
</template>

<style lang="scss" scoped>
    .filter-bar{
        @apply flex justify-between items-center;

        span{
            @apply flex;
        }
    }
</style>