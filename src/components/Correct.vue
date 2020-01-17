<template>
    <div class="success">
        <div>That's Correct!</div>
        <hr />
        <button class="btn btn-primary" @click="newQuestion()">Next Question</button>
    </div>
</template>

<script>
export default {
    methods: {
        newQuestion() {
            console.log("newQ");
            this.$emit("newQuestion", "hej");
        }
    }
};
</script>

<style>
.success {
    font: 1000;
    font-size: 50px;
    text-align: center;
    width: 600px;
    height: 200px;
    margin: auto;
    color: #3c763d;
    background-color: #dff0d8;
    border-color: #d6e9c6;
    padding: 15px;
    margin-bottom: 20px;
    border: 1px solid transparent;
    border-radius: 4px;
}
.success hr {
    border: solid lightgray 0.5px;
}
</style>