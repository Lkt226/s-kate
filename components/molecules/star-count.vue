<template>
    <span>
        <icon name="star" v-for="i in star_controller().in" :key="i.id" size="sm"
        /><icon name="star" v-for="i in star_controller().out" :key="i.id" type="far" size="sm"/>
    </span>
</template>

<script>
export default {
    props:{
        points: {
            type: Number,
            required: true
        },
    },
    methods:{
        star_controller(){
            const limit = 5, star_out = [], star_in = [];
            const counter = limit - this.points;
            
            for(let i = 0; i < this.points; i++){ star_in.push(i); }
            for(let i = 0; i < counter; i++){ star_out.push(i); }

            return {
                'in': star_in,
                'out': star_out
            }
        }
    }
}
</script>