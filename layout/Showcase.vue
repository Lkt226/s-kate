<template>
    <Base>
        <FilterBar/>
        <FilterAside :orders="filter_aside"/>
        
    </Base>
</template>

<script>
export default {
    props: {
        filters: {
            type: Object,
            required: true
        },
    },
    data(){
        return {
            filter_bar: {
                
            },
        }
    }
}
</script>