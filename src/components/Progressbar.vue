<template>
    <div class="wrapper">
        <div
            class="progressBar"
            style="background-color: green; margin: 0; color: white;"
            :style="{width: counter + '0%'}"
        ></div>
    </div>
</template>

<script>
export default {
    props: ["counter"]
};
</script>

<style>
.progressBar {
    width: 100%;
    height: 40px;
    background-color: #eee;
    margin: auto;
    transition: width 500ms;
}
</style>