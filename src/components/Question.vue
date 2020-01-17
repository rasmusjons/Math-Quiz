<template>
    <div>
        <div class="container">
            <b>What is {{numberA}} + {{numberB}}</b>
        </div>
    </div>
</template>

<script>
export default {
    props: ["numberA", "numberB"]
};
</script>
<style  scoped>
.container {
    width: 100%;
    text-align: center;
    padding: 10px;
    background-color: #f7f7f7;
}
</style>>
