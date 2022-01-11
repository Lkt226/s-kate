<template>
    <div class="label-dropdown">
        <label :for="title">{{title}}</label>
        <select :id="title">
            <option v-for="(item, index) in items" :key="index"
                :value="item.value">{{item.text}}</option>
        </select>
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
            require: false,
        },
    },
}
</script>