<template>
        <h1 v-bind="data">{{hello.toLowerCase()}}</h1>
        <h2>{{ 100*200 }}</h2>
        <h3>{{ helloFunction() }}</h3>

        <div :class="data.class" v-html="hello"></div>

        <button :disabled="buttonDisabled">This is button</button>
</template>

<script setup>
console.info("Hello vue");

const hello = "<h1>Hello Vue</h1>";
const buttonDisabled = false;

const data = {
    class: "hello",
    id: "hello",
}

function helloFunction() {
    return "Hello World";
}

</script>

<style scoped>
.hello {
    color: green;
}
</style>