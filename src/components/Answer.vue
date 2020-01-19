<template>
    <div>
        <ul>
            <li v-for="(answer, index) in answers" @click="display(index)">
                {{ answer }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: ['answers', 'numberA', 'numberB'],

        methods: {
            display(index) {
                this.$emit('clickedAnswer', index);
            },
        },
    };
</script>

<style scoped>
    ul {
        column-count: 2;
        width: 600px;
        height: 100%;

        padding: 10px;
        display: inline-block;
    }

    li {
        text-align: center;
        display: list-item;
        margin-left: 30%;
        background-color: #374dc5;
        color: white;
        padding: 15px;
        width: 20%;
        border-radius: 25%;
        margin-bottom: 30px;
    }
</style>
