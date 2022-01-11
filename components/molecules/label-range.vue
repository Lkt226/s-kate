<template>
    <div class="label-range">
        <label :for="title">{{title}}</label>
        <input type="range" :id="title">
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: '',
        },
        items: {
            type: Array,
            default: () => [
                {
                    value: "test1",
                    text: "/test1"
                },
                {
                    value: "test2",
                    text: "/test2"
                },
            ]
        },
        inline: {
            type: Boolean,
            default: true,
        },
    },
}
</script>