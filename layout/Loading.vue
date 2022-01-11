<template>
    <Base class="loading">
        <main>
            <h1>Carregando ...</h1>
            <pulse/>
        </main>
    </Base>
</template>

<style lang="scss" scoped>
    .loading{
        main{
            @apply flex flex-col items-center justify-center;
        }
    }
</style>
